// ============================================================
// FinSense AI
// Overall Combined Source Code
// ============================================================

// -------------------- CATEGORY RULES --------------------

const CATEGORY_KEYWORDS = {
    Food: ["swiggy", "zomato", "restaurant", "cafe"],
    Shopping: ["amazon", "flipkart", "mall"],
    Transport: ["uber", "ola", "metro", "fuel"],
    Entertainment: ["netflix", "spotify", "movie"],
    Bills: ["electricity", "mobile", "internet", "rent"]
};

const MONTHLY_BUDGETS = {
    Food: 5000,
    Shopping: 4000,
    Transport: 3000,
    Entertainment: 2000,
    Bills: 6000,
    Others: 3000
};


// -------------------- SAMPLE TRANSACTIONS --------------------

let transactions = [
    { date: "2026-08-01", merchant: "Swiggy", amount: 350, type: "expense" },
    { date: "2026-08-02", merchant: "Uber", amount: 250, type: "expense" },
    { date: "2026-08-03", merchant: "Amazon", amount: 1500, type: "expense" },
    { date: "2026-08-04", merchant: "Netflix", amount: 649, type: "expense" },
    { date: "2026-08-05", merchant: "Salary", amount: 30000, type: "income" }
];


// -------------------- CATEGORISE TRANSACTION --------------------

function categorizeTransaction(merchant) {

    merchant = merchant.toLowerCase();

    for (const category in CATEGORY_KEYWORDS) {

        for (const keyword of CATEGORY_KEYWORDS[category]) {

            if (merchant.includes(keyword)) {
                return category;
            }
        }
    }

    return "Others";
}


// -------------------- ADD TRANSACTION --------------------

function addTransaction(date, merchant, amount, type) {

    const category = categorizeTransaction(merchant);

    const transaction = {
        id: Date.now(),
        date,
        merchant,
        amount: Number(amount),
        type,
        category
    };

    transactions.push(transaction);

    return transaction;
}


// -------------------- SPENDING ANALYSIS --------------------

function analyzeSpending() {

    let totalIncome = 0;
    let totalSpending = 0;

    let categorySpending = {};

    transactions.forEach(transaction => {

        // Automatically categorise
        transaction.category =
            categorizeTransaction(transaction.merchant);

        if (transaction.type === "income") {

            totalIncome += transaction.amount;

        } else {

            totalSpending += transaction.amount;

            if (!categorySpending[transaction.category]) {
                categorySpending[transaction.category] = 0;
            }

            categorySpending[transaction.category] +=
                transaction.amount;
        }
    });

    const savings = totalIncome - totalSpending;

    return {
        totalIncome,
        totalSpending,
        savings,
        categorySpending
    };
}


// -------------------- HEALTH SCORE --------------------

function calculateHealthScore(analysis) {

    let score = 100;

    // Spending more than income
    if (analysis.totalSpending > analysis.totalIncome) {
        score -= 40;
    }

    // Savings below 20%
    if (analysis.totalIncome > 0) {

        const savingsPercentage =
            (analysis.savings / analysis.totalIncome) * 100;

        if (savingsPercentage < 20) {
            score -= 20;
        }
    }

    // Check category budgets
    for (const category in analysis.categorySpending) {

        const spent =
            analysis.categorySpending[category];

        const budget =
            MONTHLY_BUDGETS[category] || 3000;

        if (spent > budget) {
            score -= 10;
        }
    }

    if (score < 0) {
        score = 0;
    }

    return score;
}


// -------------------- AI NUDGE ENGINE --------------------

function generateNudges(analysis) {

    let nudges = [];

    // Overspending
    if (analysis.totalSpending > analysis.totalIncome) {

        nudges.push({
            type: "warning",
            message:
                "Your monthly spending is greater than your income. Reduce unnecessary expenses."
        });
    }

    // Category budget analysis
    for (const category in analysis.categorySpending) {

        const spent =
            analysis.categorySpending[category];

        const budget =
            MONTHLY_BUDGETS[category] || 3000;

        if (spent > budget) {

            const excess = spent - budget;

            nudges.push({
                type: "overspending",
                message:
                    `You spent ₹${excess.toFixed(2)} above your ${category} budget.`
            });
        }
    }

    // Investment nudge
    if (analysis.savings > 1000) {

        const investmentAmount =
            analysis.savings * 0.20;

        nudges.push({
            type: "investment",
            message:
                `You can consider investing ₹${investmentAmount.toFixed(2)} from your monthly savings.`
        });
    }

    // Low savings
    if (analysis.savings <= 0) {

        nudges.push({
            type: "saving",
            message:
                "Try saving small amounts from daily expenses before investing."
        });
    }

    // Subscription nudge
    if (analysis.categorySpending["Entertainment"] > 1000) {

        nudges.push({
            type: "subscription",
            message:
                "Review your entertainment subscriptions to reduce recurring expenses."
        });
    }

    // Spare change investment
    nudges.push({
        type: "round-up",
        message:
            "Round up your daily expenses and invest the spare change."
    });

    return nudges;
}


// -------------------- INVESTMENT PROJECTION --------------------

function calculateInvestmentGrowth(
    amount,
    ratePercent,
    years
) {

    const rate = ratePercent / 100;

    const futureValue =
        amount * Math.pow(1 + rate, years);

    return {
        investedAmount: amount,
        futureValue: Number(
            futureValue.toFixed(2)
        ),
        profit: Number(
            (futureValue - amount).toFixed(2)
        )
    };
}


// -------------------- SIP PROJECTION --------------------

function calculateSIP(
    monthlyAmount,
    ratePercent,
    years
) {

    const monthlyRate =
        ratePercent / 100 / 12;

    const months = years * 12;

    const futureValue =
        monthlyAmount *
        ((Math.pow(1 + monthlyRate, months) - 1)
        / monthlyRate) *
        (1 + monthlyRate);

    return {
        totalInvestment:
            monthlyAmount * months,

        futureValue:
            Number(futureValue.toFixed(2)),

        profit:
            Number(
                (
                    futureValue -
                    monthlyAmount * months
                ).toFixed(2)
            )
    };
}


// -------------------- SAVINGS GOALS --------------------

let goals = [
    {
        id: 1,
        name: "Emergency Fund",
        targetAmount: 50000,
        savedAmount: 15000
    },
    {
        id: 2,
        name: "Laptop",
        targetAmount: 80000,
        savedAmount: 30000
    }
];


// -------------------- CREATE GOAL --------------------

function createGoal(name, targetAmount) {

    const goal = {

        id: Date.now(),

        name,

        targetAmount:
            Number(targetAmount),

        savedAmount: 0
    };

    goals.push(goal);

    return goal;
}


// -------------------- ADD CONTRIBUTION --------------------

function contributeToGoal(id, amount) {

    const goal =
        goals.find(
            g => g.id == id
        );

    if (!goal) {
        return null;
    }

    goal.savedAmount +=
        Number(amount);

    return goal;
}


// -------------------- GOAL PROGRESS --------------------

function getGoalProgress(goal) {

    const progress =
        (goal.savedAmount /
        goal.targetAmount) * 100;

    let milestone = "Getting Started";

    if (progress >= 100) {
        milestone = "Goal Achieved";
    }

    else if (progress >= 75) {
        milestone = "Almost There";
    }

    else if (progress >= 50) {
        milestone = "Halfway Hero";
    }

    else if (progress >= 25) {
        milestone = "Beginner Saver";
    }

    return {

        ...goal,

        progress:
            Math.min(
                progress,
                100
            ).toFixed(2),

        milestone
    };
}


// -------------------- FINAL DASHBOARD DATA --------------------

function getDashboardData() {

    const analysis =
        analyzeSpending();

    const healthScore =
        calculateHealthScore(
            analysis
        );

    const nudges =
        generateNudges(
            analysis
        );

    const goalProgress =
        goals.map(
            getGoalProgress
        );

    return {

        analysis,

        healthScore,

        nudges,

        goals:
            goalProgress
    };
}


// ============================================================
// PROGRAM EXECUTION
// ============================================================

const result =
    getDashboardData();

console.log(
    "========== FinSense AI =========="
);

console.log(
    "\nSPENDING ANALYSIS"
);

console.log(
    result.analysis
);

console.log(
    "\nSPENDING HEALTH SCORE:"
);

console.log(
    result.healthScore
);

console.log(
    "\nAI FINANCIAL NUDGES:"
);

console.log(
    result.nudges
);

console.log(
    "\nSAVINGS GOALS:"
);

console.log(
    result.goals
);

console.log(
    "\nINVESTMENT PROJECTION:"
);

console.log(
    calculateInvestmentGrowth(
        10000,
        10,
        5
    )
);

console.log(
    "\nSIP PROJECTION:"
);

console.log(
    calculateSIP(
        2000,
        12,
        5
    )
);
