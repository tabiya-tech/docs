# Web Application

For ease of use, we developed a simple FullStack application (a Flask-based API as a BackEnd and jQuery FrontEnd) to analyze job descriptions and predict relevant occupations, skills, and qualifications using the entity-linking model.

### Usage

First, activate the virtual environment as explained [here](getting-started.md#dep). Then, run the following command in python in the `root` directory:

#### Running the API

**Run the Flask application**:

```bash
python app/server/matching.py
```

Or set the Flask application environment variable and use the Flask command:

```bash
export FLASK_APP=app/server/matching.py
flask run --host=0.0.0.0 --port=5001
```

### Example Usage

1. **Open the browser** and navigate to `http://127.0.0.1:5001/`.
2. **Paste a job description** into the provided text area.
3. **Click the "Analyze Job" button** to send the job description to the `/match` endpoint.
4. **View the results** under "Predicted Occupations," "Predicted Skills," and "Predicted Qualifications."

{% hint style="danger" %}
This app is just for demonstration purposes. If you wish to deploy this model, use a more reliable/secure strategy.
{% endhint %}
