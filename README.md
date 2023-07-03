import openpyxl

def create_salary_schedule():
    workbook = openpyxl.Workbook()
    sheet = workbook.active

    sheet.append(["Year", "Salary", "Incentive", "Total Salary", "Global Increase", "Expected Increase"])

    for year in range(2010, 2016):
        salary = 3000
        incentive = salary * 0.1
        total_salary = salary + incentive
        global_increase = 5
        expected_increase = global_increase * salary

        sheet.append([year, salary, incentive, total_salary, global_increase, expected_increase])

    workbook.save("salary_schedule.xlsx")

if __name__ == "__main__":
    create_salary_schedule()
