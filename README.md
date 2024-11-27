from data_loader import DataLoader
from demographic_group import DemographicGroup

# Load and clean data
file_path = r"C:\Users\hp\Desktop\Python proj\data.csv"
data_loader = DataLoader(file_path)
data = data_loader.load_data()
cleaned_data = data_loader.clean_data()

# Individual Region Analysis
region = 'Urban' 
region_data = cleaned_data[cleaned_data['Location'] == region]
region_group = DemographicGroup(region_data, region_name=region)
region_group.summary_statistics()
region_group.plot_data()



