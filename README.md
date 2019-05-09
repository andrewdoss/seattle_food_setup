### Seattle Food Setup

seattle-food-setup.ipynb - a notebook showing the data preprocessing steps

data/ - the subdirectory where the data files go
  1. restaurants.csv - data about the restaurants in Yelp!
  2. Food_Establishment_Inspection_Data.csv - King County inspections data
  3. reviews.csv - too large for github, download here: http://www.cs.stonybrook.edu/~junkang/hygiene/data/reviews.csv.gz

### (non-standard) Required packages

numpy
pandas
matplotlib
seaborn
usaddress
nltk
scipy

### Assumptions/preprocessing decisions:
1. Dropped early years with very view reviews   
2. Dropped 'Consultation/Education' inspection types as they are not for enforcing compliance
3. Dropped restaurants in Yelp! list without a valid street address
4. Merged Yelp! entities for restaurants with same address and at least one non-trivial overlapping name token
5. Dropped restaurants that did not match to inspection record, including partial name match
6. Dropped restaurants with more than 22 inspections as those outliers represent businesses with multiple inspection entities per a single Yelp! entity (e.g. Costco)
7. Formed basic time series features and dropped first inspection for each restaurant
due to lack of ability to compute time series features.
8. Dropped return inspections, as mandatory return inspections would not benefit from prioritization as much as random inspections and because return inspections follow
a different distribution
