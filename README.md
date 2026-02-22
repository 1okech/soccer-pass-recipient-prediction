# soccer-pass-recipient-prediction

End-to-end ML pipeline for predicting soccer pass recipients from spatiotemporal tracking data, combining spatial feature engineering with probabilistic modeling.

OVERVIEW
Passing decisions in soccer occur under tight constraints, spatial and temporal. This project builds a machine learning system that predicts the intended receiver of a pass using player tracking data at the time of pass initiation.

Using engineered spatial features and probabilistic modeling, the system learns how player positioning and field context influence passing decisions.

Key goals:

Model real-world passing behavior
Compare ML models against heuristic baselines
Quantify predictive performance using ranking metrics
Bridge sports intuition with data-driven analysis

DATASET
Source: Metrica Sports tracking data
Type: Spatiotemporal player tracking
Granularity: Frame-level positional data
Prediction task: Multiclass classification over teammates

Each pass event is represented using player and ball positions at the time of pass initiation.

Feature Engineering
To capture tactical context, the following spatial features were engineered:

    Inter-player distances
    Passer → teammate distances
    Relative angles between players
    Spatial ordering of teammates
    Local positional context

These features transform raw tracking data into structured inputs suitable for machine learning models.

Models
Baseline
Nearest-teammate heuristic
Chooses the physically closest teammate to the passer
Serves as a simple tactical baseline

Machine Learning Models
Logistic Regression with softmax output
Neural Network classifier
The models output a probability distribution over all eligible teammates.

Evaluation Metrics

Because this is a ranking problem, multiple metrics were used:

    Top-1 Accuracy — correct receiver predicted
    Top-3 Accuracy — true receiver in top three
    Average Rank — mean position of true receiver

These metrics better capture decision quality than raw accuracy alone.

Results

Key takeaway:
The machine learning models significantly outperform the nearest-teammate heuristic, demonstrating that passing decisions depend on richer spatial context beyond simple proximity.

Future Work

Incorporate temporal sequence models
Add defender pressure features
Explore graph neural networks
Build real-time inference pipeline
Deploy interactive tactical dashboard

Author
Isaac Okech Were
Stanford University - Computer Science
