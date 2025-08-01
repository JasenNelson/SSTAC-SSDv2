# Species Sensitivity Distribution (SSD) Generator Version 2

A Streamlit-based web application for generating Species Sensitivity Distribution (SSD) plots following the CCME Protocol for the Protection of Aquatic Life. This application now features a live, online toxicology database that is autonomously populated and updated by an AI agent, providing a dynamic and growing resource for ecotoxicological analysis.

## Features

- Dynamic Toxicology Database: Access a growing database of toxicology data, powered by a Supabase (PostgreSQL) backend.

- AI-Powered Data Collection: The database is automatically populated by an AI agent that extracts and validates data from public scientific literature sources, ensuring the data is current and comprehensive.

- Flexible Data Sources: Choose between searching the live online database for curated data or uploading your own private CSV file for analysis.

- Comprehensive SSD Analysis: Generate SSD plots using Log-Normal, Log-Logistic, or Weibull distributions to fit your data.

- CCME Alignment: Data processing, filtering, and analysis options follow the guidelines established by the Canadian Council of Ministers of the Environment (CCME) for protecting aquatic life.

- Interactive Visualization: Explore results with interactive Plotly graphs, complete with 95% confidence intervals and detailed hover-over information.

- Transparent Data Sourcing: View detailed source and citation information for the data used in your analysis, including authors, publication years, and DOIs.

## Backend

- The application's backend is built on Supabase, a robust and scalable PostgreSQL database.
- 

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/JasenNelson/SSTAC.git
   cd SSTAC
   ```

2. Create a virtual environment (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: .\venv\Scripts\activate
   ```

3. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```
   This will install all necessary libraries, including streamlit, pandas, supabase, and st-supabase-connection.

## Configuration

To connect to the online database, you need to provide your Supabase credentials. Create a file named secrets.toml in a .streamlit directory at the root of your project.
   # .streamlit/secrets.toml
   [connections.supabase]
   url = "YOUR_SUPABASE_URL"
   key = "YOUR_SUPABASE_ANON_KEY"


## Usage

1. Run the application:
   ```bash
   streamlit run ssd_app_v2.py
   ```

2. Open your web browser and navigate to the provided local URL (typically http://localhost:8501)

3. Select your data source (upload a file or use the built-in database)

4. Choose the chemicals and parameters for your analysis

5. Click "Generate SSD" to create the plot

## Data Format

When uploading your own data, ensure it follows this format:

- `chemical_name`: Name of the chemical
- `species_scientific_name`: Scientific name of the species
- `broad_group`: Taxonomic group
- `conc1_mean`: Mean concentration value
- `endpoint`: Type of endpoint measurement
- Additional metadata columns as needed

## Online Database Schema

The online database provides a richer dataset, including detailed citation and source metadata for enhanced traceability and context. Key fields include:

- Core toxicity data (chemical_name, species_scientific_name, conc1_mean, endpoint)

- Detailed source information (author, title, publication_year)

- Reference identifiers (doi, source_url)

- Data quality and validation fields


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Contact

For questions or feedback, please open an issue on GitHub.
