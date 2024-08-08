# GitHub Repository Analysis

This project aims to analyze repositories from specific organizations on GitHub and collect data about the repositories.

## Installation

To run this project, you will need to install the following Python libraries:
- `PyGithub`
- `python-dotenv`
- `pandas`
- `tqdm`
- `matplotlib`
- `seaborn`

## Configuration

1. Create a `.env` file in the root directory of the project and add your GitHub token as `GITHUB_TOKEN`.
2. Update the list of organizations and excluded repositories as needed.

## Features

### Main Functions

1. **Repository Data Collection**
   - **fetch_organization_repositories(organization_name, language=None)**
     - Collects data about repositories from a specific organization on GitHub. Filters out excluded repositories and applies specific validity criteria based on the organization.

2. **CSV File Generation with Repository Metrics**
   - **generate_metrics_csv()**
     - Generates a CSV file containing detailed data on the analyzed repositories, including information such as name, URL, primary language, creation and update dates, size, star count, watchers count, forks count, open issues count, subscribers count, and total lines of code.

3. **Programming Language Usage Calculation**
   - **calculate_language_usage(dataframe)**
     - Calculates the usage of programming languages in the analyzed repositories based on the number of lines in each language, generating a CSV with the percentage distribution of each language and the total lines of code per language.

4. **Graph Generation**
   - **plot_metrics_distribution()**
     - Generates distribution charts for each of the analyzed metrics, showing frequency and central tendency (mean and median).
   - **plot_boxplot_metrics()**
     - Generates boxplots to visualize the dispersion and possible outliers in key repository metrics.
   - **plot_metrics_statistics()**
     - Generates charts with descriptive statistics for key repository metrics (e.g., stars, watchers, forks, open issues, subscribers, network size).

### Statistics Generation

1. **generate_statistics(dataframe)**
   - Generates descriptive statistics for key repository metrics, such as mean, median, mode, and standard deviation. Results are saved in a CSV file.

### Table Structure

#### Repository Table (codesamples.csv)

- **full_name**: Full name of the repository (e.g., `organization/repo_name`)
- **name**: Repository name
- **owner**: Repository owner
- **html_url**: Repository URL on GitHub
- **description**: Repository description
- **language**: Primary language of the repository
- **created_at**: Repository creation date
- **updated_at**: Last update date of the repository
- **pushed_at**: Date of the last push to the repository
- **size**: Repository size in KB
- **stargazers_count**: Number of stars on the repository
- **watchers_count**: Number of watchers of the repository
- **forks_count**: Number of forks of the repository
- **open_issues_count**: Number of open issues in the repository
- **subscribers_count**: Number of subscribers to the repository
- **network_count**: Number of repositories in the network (total forks)
- **archived**: Indicates if the repository is archived
- **total_lines**: Total number of lines of code in the repository
- **langs_percentage**: Percentage distribution of programming languages in the repository

#### Language Usage Table (languages_usage.csv)

- **Language**: Programming language name
- **Usage Percentage**: Percentage of the language used in the total lines of code
- **Lines**: Total number of lines of code written in the language

#### Statistics Table (statistics.csv)

- **mean**: Mean of the metrics
- **median**: Median of the metrics
- **mode**: Mode of the metrics
- **std**: Standard deviation of the metrics

### Results

The results of the analyzed data will be saved in the `results` folder:
- `codesamples.csv`: Repository data.
- `languages_usage.csv`: Programming language usage.
- `statistics.csv`: Descriptive statistics of repository metrics.
- `language_usage_charts.png`: Charts of programming language usage.
- `distribution_metrics.png`: Charts of metric distributions.
- `boxplot_metrics.png`: Boxplots of metrics.
- `desc_stats.png`: Charts of descriptive statistics.
