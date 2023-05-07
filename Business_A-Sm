import pandas as pd
import matplotlib.pyplot as plt

class BusinessAnalyticsSystem:
    def __init__(self):
        self.data = pd.DataFrame(columns=['Date', 'Sales', 'Expenses'])
    
    def collect_data(self, date, sales, expenses):
        new_data = pd.DataFrame([[date, sales, expenses]], columns=['Date', 'Sales', 'Expenses'])
        self.data = pd.concat([self.data, new_data], ignore_index=True)
    
    def process_data(self):
        self.data['Profit'] = self.data['Sales'] - self.data['Expenses']
    
    def visualize_data(self):
        plt.plot(self.data['Date'], self.data['Sales'], label='Sales')
        plt.plot(self.data['Date'], self.data['Expenses'], label='Expenses')
        plt.plot(self.data['Date'], self.data['Profit'], label='Profit')
        plt.xlabel('Date')
        plt.ylabel('Amount')
        plt.title('Business Performance')
        plt.legend()
        plt.show()
    
    def generate_report(self):
        report = self.data.groupby(pd.Grouper(key='Date', freq='M')).sum().reset_index()
        report['Profit Margin'] = (report['Profit'] / report['Sales']) * 100
        return report


# Example usage:

# Create a business analytics system
analytics_system = BusinessAnalyticsSystem()

# Collect data
analytics_system.collect_data('2023-01-01', 50000, 35000)
analytics_system.collect_data('2023-02-01', 60000, 40000)
analytics_system.collect_data('2023-03-01', 70000, 45000)
analytics_system.collect_data('2023-04-01', 55000, 38000)

# Process data
analytics_system.process_data()

# Visualize data
analytics_system.visualize_data()

# Generate report
report = analytics_system.generate_report()
print(report)
