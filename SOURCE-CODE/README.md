FinSense AI – Overall Source Code
```
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

let transactions = [
    { date: "2026-08-01", merchant: "Swiggy", amount: 350, type: "expense" },
    { date: "2026-08-02", merchant: "Uber", amount: 250, type: "expense" },
    { date: "2026-08-03", merchant: "Amazon", amount: 1500, type: "expense" },
    { date: "2026-08-04", merchant: "Netflix", amount: 649, type: "expense" },
    { date: "2026-08-05", merchant: "Salary", amount: 30000, type: "income" }
];

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

function addTransaction(date, merchant, amount, type) {
    const transaction = {
        id: Date.now(),
        date: date,
        merchant: merchant,
        amount: Number(amount),
        type: type,
        category: categorizeTransaction(merchant)
    };

    transactions.push(transaction);

    return transaction;
}

function analyzeSpending() {
    let totalIncome = 0;
    let totalSpending = 0;
    let categorySpending = {};

    transactions.forEach(transaction => {
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

function calculateHealthScore(analysis) {
    let score = 100;

    if (analysis.totalSpending > analysis.totalIncome) {
        score -= 40;
    }

    if (analysis.totalIncome > 0) {
        const savingsPercentage =
            (analysis.savings / analysis.totalIncome) * 100;

        if (savingsPercentage < 20) {
            score -= 20;
        }
    }

    for (const category in analysis.categorySpending) {
        const spent = analysis.categorySpending[category];
        const budget =
            MONTHLY_BUDGETS[category] || 3000;

        if (spent > budget) {
            score -= 10;
        }
    }

    return Math.max(score, 0);
}

function generateNudges(analysis) {
    let nudges = [];

    if (analysis.totalSpending > analysis.totalIncome) {
        nudges.push(
            "Your spending is greater than your income."
        );
    }

    for (const category in analysis.categorySpending) {
        const spent = analysis.categorySpending[category];
        const budget =
            MONTHLY_BUDGETS[category] || 3000;

        if (spent > budget) {
            const excess = spent - budget;

            nudges.push(
                `You spent ₹${excess} above your ${category} budget.`
            );
        }
    }

    if (analysis.savings > 1000) {
        const investmentAmount =
            analysis.savings * 0.20;

        nudges.push(
            `You can invest ₹${investmentAmount.toFixed(2)} from your savings.`
        );
    }

    if (analysis.savings <= 0) {
        nudges.push(
            "Try reducing unnecessary expenses and start saving."
        );
    }

    if (
        analysis.categorySpending["Entertainment"] > 1000
    ) {
        nudges.push(
            "Review entertainment subscriptions to reduce expenses."
        );
    }

    nudges.push(
        "Round up your daily expenses and invest the spare change."
    );

    return nudges;
}

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
        futureValue: Number(futureValue.toFixed(2)),
        profit: Number(
            (futureValue - amount).toFixed(2)
        )
    };
}

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
        totalInvestment: monthlyAmount * months,
        futureValue: Number(futureValue.toFixed(2)),
        profit: Number(
            (
                futureValue -
                monthlyAmount * months
            ).toFixed(2)
        )
    };
}

function createGoal(name, targetAmount) {
    const goal = {
        id: Date.now(),
        name: name,
        targetAmount: Number(targetAmount),
        savedAmount: 0
    };

    goals.push(goal);

    return goal;
}

function contributeToGoal(id, amount) {
    const goal = goals.find(
        g => g.id == id
    );

    if (!goal) {
        return null;
    }

    goal.savedAmount += Number(amount);

    return goal;
}

function getGoalProgress(goal) {
    const progress =
        (goal.savedAmount / goal.targetAmount) * 100;

    let milestone = "Getting Started";

    if (progress >= 100) {
        milestone = "Goal Achieved";
    } else if (progress >= 75) {
        milestone = "Almost There";
    } else if (progress >= 50) {
        milestone = "Halfway Hero";
    } else if (progress >= 25) {
        milestone = "Beginner Saver";
    }

    return {
        ...goal,
        progress: Math.min(progress, 100).toFixed(2),
        milestone: milestone
    };
}

function getDashboardData() {
    const analysis = analyzeSpending();

    const healthScore =
        calculateHealthScore(analysis);

    const nudges =
        generateNudges(analysis);

    const goalProgress =
        goals.map(getGoalProgress);

    return {
        analysis: analysis,
        healthScore: healthScore,
        nudges: nudges,
        goals: goalProgress
    };
}

const result = getDashboardData();

console.log("========== FinSense AI ==========");

console.log("SPENDING ANALYSIS");
console.log(result.analysis);

console.log("SPENDING HEALTH SCORE");
console.log(result.healthScore);

console.log("AI FINANCIAL NUDGES");
console.log(result.nudges);

console.log("SAVINGS GOALS");
console.log(result.goals);

console.log("INVESTMENT PROJECTION");
console.log(
    calculateInvestmentGrowth(10000, 10, 5)
);

console.log("SIP PROJECTION");
console.log(
    calculateSIP(2000, 12, 5)
);
```
