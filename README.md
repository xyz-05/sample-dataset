# sample-dataset
import matplotlib.pyplot as plt
import pandas as pd


class DataVisualizer:
    def __init__(self, data):
        self.data = data
    def create_bar_chart(self, column_name):
        plt.figure(figsize=(8, 6))
        self.data[column_name].value_counts().plot(kind='bar')
        plt.title(f'Distribution of {column_name}')
        plt.xlabel(column_name)
        plt.ylabel('Count')
        # plt.show()

    def create_histogram(self, column_name, bins=5):
        plt.figure(figsize=(8, 6))
        self.data[column_name].hist(bins=bins, edgecolor='black')
        plt.title(f'Distribution of {column_name}')
        plt.xlabel(column_name)
        plt.ylabel('Frequency')
        plt.show()


# Sample dataset
data = {
'Age': [20, 21, 19, 24, 28, 25, 30, 22, 26, 27],
'Gender': ['Male', 'Female', 'Male', 'Female', 'Male', 'Female', 'Male', 'Female', 'Male', 'Female']
}

df = pd.DataFrame(data)

# Create an instance of the DataVisualizer class
visualizer = DataVisualizer(df)

# Create a bar chart for gender distribution
visualizer.create_bar_chart('Gender')

# Create a histogram for age distribution
visualizer.create_histogram('Age')
