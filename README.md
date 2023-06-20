```python
from dataclasses import dataclass, field
from typing import List, Dict

@dataclass
class My_Info:
    name: str = "Carlos"
    nationality: str = "Spanish"
    languages: List[str] = field(init=False, default_factory=list)
    markup_languages: List[str] = field(init=False, default_factory=list)
    technologies: Dict[str, List[str]] = field(init=False, default_factory=dict)
        
    def __post_init__(self) -> None:
        self.languages = ["Python",
                          "JavaScript"]
        
        self.markup_languages = ["html",
                                 "css"]
        
        self.technologies = {"machine_learning": ["TensorFlow",
                                                  "Keras"
                                                  "scikit-learn"],
                             "data_science": ["NumPy",
                                              "Pandas",
                                              "Matplotlib"],
                             "backend": ["Django",
                                         "Flask",
                                         "FastAPI"],
                             "frontend": ["html, css & js"]} # No fancy frameworks, yet...


    def __str__(self) -> str:
        return f"Name: {self.name}\nNationality: {self.nationality}\nDescription: Fullstack developer & Machine learning engineer"
    
me = My_Info()
print(me)
```
