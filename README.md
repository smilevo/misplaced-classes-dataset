# Misplaced Classes Detection Dataset

This repository contains the dataset used in the research paper, "Detecting and Moving Misplaced Classes in Software Packages." The dataset consists of CSV files, each containing the analysis results for a specific Java project. Our tool, ClassMoveExplorer, analyzed these projects to identify misplaced classes and suggest better package locations.

## Dataset Structure

The dataset is organized into four categories based on the project's origin and domain:

- **`data/apache-projects`**: Contains analysis results for projects from the Apache Software Foundation.
- **`data/google-projects`**: Contains analysis results for projects from Google.
- **`data/spring-projects`**: Contains analysis results for projects from the Spring ecosystem.
- **`data/other-projects`**: Contains analysis results for other open-source projects.

Each CSV file is named after the project it represents (e.g., `apache-nifi.csv`).

## File Format

Each CSV file has the following columns:

| Column Name          | Description                                                                                             | Example                                                                 |
| -------------------- | ------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `class_id`           | A unique identifier for the class.                                                                      | `ArticleApi`                                                            |
| `class_name`         | The name of the Java class.                                                                             | `ArticleApi`                                                            |
| `current_package`    | The package where the class is currently located.                                                       | `io.spring.api`                                                         |
| `is_misplaced`       | A boolean value (`True` or `False`) indicating whether the class is considered misplaced.                 | `True`                                                                  |
| `confidence`         | A numeric score (0.0 to 1.0) representing the confidence in the `is_misplaced` prediction.              | `0.6`                                                                   |
| `reasoning`          | A brief explanation of why the class is considered misplaced.                                           | `Contains controller-typical methods: deleteArticle`                    |
| `suggested_package`  | The recommended package for the class if it is misplaced.                                               | `controller`                                                            |
| `evidence`           | The specific evidence from the source code that supports the reasoning.                                 | `Annotations: RestController, RequestMapping; Methods: deleteArticle` |
| `method_used`        | The analysis method used to make the prediction.                                                        | `rule-based + semantic analysis`                                        |
| `analysis_time`      | The time taken for the analysis in seconds.                                                             | `3.57`                                                                  |
| `analysis_timestamp` | The timestamp of when the analysis was performed.                                                       | `2025-08-06T00:26:10.560069`                                            |

## Project Summary

The following table provides a summary of the projects included in this dataset:

| Project                                    | Total Classes | Misplaced Classes |
| ------------------------------------------ | ------------- | ----------------- |
| **Spring Projects**                        |               |                   |
| spring-petclinic                           | 71            | 0                 |
| spring-boot-realworld-example-app          | 123           | 11                |
| spring-boot-lean-realworld-example-app   | 81            | 0                 |
| spring-boot-web-application-sample       | 173           | 0                 |
| booking-microservices-java-spring-boot   | 247           | 0                 |
| **Apache Projects**                        |               |                   |
| apache-nifi                                | 10130         | 662               |
| apache-kafka                               | 9540          | 309               |
| apache-commons-lang                        | 2296          | 9                 |
| apache-storm-crawler                       | 388           | 0                 |
| **Google Projects**                        |               |                   |
| google-guava                               | 9656          | 40                |
| openrefine                                 | 1349          | 13                |
| **Other Projects**                         |               |                   |
| elasticsearch                              | 37812         | 463               |
| deeplearning4j                             | 6031          | 104               |
| junit5                                     | 4735          | 36                |
| jenkins                                    | 4199          | 82                |
| retrofit                                   | 798           | 91                |
| openmrs-core                               | 2072          | 124               |
| javapoet                                   | 286           | 7                 |

## How to Use This Dataset

This dataset can be used for a variety of research purposes, including:

- **Replicating the results** of our study.
- **Evaluating other code smell detection tools** by comparing their results to ours.
- **Training and testing new machine learning models** for code refactoring and architectural analysis.
- **Conducting further studies** on the nature and impact of misplaced classes in software projects.

## Citation

If you use this dataset in your research, please cite our paper:

```
[Your Paper Citation Here]
```

## License

This dataset is released under the [MIT License](LICENSE).
