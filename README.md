```python
from dataclasses import dataclass, field

@dataclass
class MyInfo:
    name: str = "Carlos"
    nationality: str = "Spanish"
    languages: list[str] = field(init=False, default_factory=list)
    markup_languages: list[str] = field(init=False, default_factory=list)
    technologies: dict[str, list[str]] = field(init=False, default_factory=dict)
        
    def __post_init__(self) -> None:
        self.languages = ["Python",
                          "JavaScript/Typescript",
                          "C#",
                          "C/C++"]
        
        self.markup_languages = ["html",
                                 "css"]
        
        self.technologies = {"machine_learning": ["TensorFlow",
                                                  "Keras"
                                                  "scikit-learn"
                                                  "PyTorch"],
                             "data_science": ["NumPy",
                                              "Pandas",
                                              "Matplotlib"],
                             "backend": ["Django",
                                         "Flask",
                                         "FastAPI"],
                             "frontend": ["React"],
                             "robotics": ["Arduino"],
                             "CAD": ["Autodesk Inventor"]}


    def __str__(self) -> str:
        return f"Name: {self.name}\nNationality: {self.nationality}\nDescription: Fullstack developer & machine learning engineer"

if __name__ == "__main__":   
    me = MyInfo()
    print(me)
```
