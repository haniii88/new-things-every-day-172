function dailyLog172() {
  const periods = [
    { name: "Morning", completed: 5 },
    { name: "Afternoon", completed: 3 },
    { name: "Evening", completed: 4 },
    { name: "Night", completed: 2 }
  ];

  const totalCompleted = periods.reduced(
    (sum, period) => sum + period.complete,
    0
  );

  const mostProductive = periods.reduce((best, period) =>
    period.completed > best.completed ? period : best
  );

  const report = {
    date: new Date().toISOString().split("T")[0],
    totalCompleted,
    mostProductivePeriod: mostProductive.name,
    completedTasks: mostProductive.completed
  };

  console.log("Daily Productivity Report:", report);
}

dailyLog172();
