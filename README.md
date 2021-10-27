# Data Engineer Technical Challenge
For this project, you must use Python, but you have complete freedom over any libraries or approaches you'd like otherwise.

## Production
Using any means you like, generate a CSV file containing the following information:

1. a person's first name
2. a person's last name,
3. their birthdate,
4. their email address,
5. their home address,
6. and two (2) additional pieces of information.

For example, see the attached `medical.csv` dataset, which contains all of the above as well as a pharmaceutical prescription and dosage schedule, for 1000 fake people.

## Ingestion
Parse the CSV file you created into a list of Person objects, with fields corresponding to their personal information. Provide a class method that prints this information in a nice way to the console.

## Loading
Store all of the data from the CSV into a database (sqlite is fine) using your schema of choice. The raw data should go into a table called `raw`.

## Transforming
Choose two criteria by which to eliminate people from the dataset. Using your process of choice, clean the raw data by removing any people whose information satisfies those criteria. For example, we might wish to remove people in the provided `medical.csv` dataset who were prescribed fluoride, or who are scheduled to never take their prescriptions. Cleaned data should be stored in the database in a table called `clean`.

## Retrieval
Provide a means of querying the additional data (so, not the person's name, email, or address) by a keyword, returning a birthdate-sorted list of Person objects, if any.

## Display
Provide a means of printing out a query to the console. For the `medical.csv` example, given a valid prescription keyword, this should print a nicely-formatted list of people and their prescriptions to the console. The result could look something like the example below, but doesn't have to match it exactly. Curly braces surround variables that should be stringified.

```
{name}, born {birthdate}
Currently prescribed the following:
{prescription}
To be taken: {schedule}
Contact this patient by email at: {email}
Or by mail at {address}
```

## Documentation
Upload your solution to GitHub and provide a link to the repository. The repository README should contain a brief description of the technical choices and design decisions you made in this project. This should be things like, which libraries you used and why, why you retrieved the raw data the way you did, why you implemented keyword queries the way you did, and so on. This is an opportunity to show us how you think!

## Optional Bonus
(You don't need to do this, but it's very much nice-to-have.)

1. Load the raw and cleaned data into a cloud database, like Azure SQL, AWS RDS, or other.
2. Deploy a web service that can be queried however you like. We should be able to pass a keyword in the request and receive a JSON response.
