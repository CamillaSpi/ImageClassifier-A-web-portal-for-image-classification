# ImageClassifier: A web portal for image classification
## Overview
<div align='center'>
  <img src="Report and Presentation/Camilla/PortalMain.png" alt="Portal Web" style="width:50%; max-width:400px;">
</div>

The objective of this project was to realise a web portal for the classification of images belonging to specific macrocategories (e.g. faces, objects, landscapes), for which specific categories (e.g. gender and age for a face) were identified, in order to ensure their classification by a series of neural networks. Specifically, the images were characterised by macrocategories (Face Counting, People Counting, Vehicle Counting and Face Analysis) to which specific categories were associated: for Face Counting, People Counting
and Vehicle Counting, the selection related to the number of faces, people and vehicles was used, for the macrocategory Face Analysis the subjects of the classification were the age, gender, ethnicity and emotion of the face in the image. The neural networks used were: Count Faces, Count People, Count Vehicles, Face Bio. 
The portal was to be structured in such a way that the non-authenticated user would only see a page with 10 images, possibly divided into macrocategories, without any additional information, while the authenticated user could select a macrocategory and classify an image shown on the page, i.e. select the category to which he or she thought it belonged. The user becomes, therefore, the protagonist in the process of choosing the macrocategory, the image to be analysed
and in selecting among the neural networks reported as compatible. At the end of the process
the user can compare the values he/she has set for the different categories with those suggested by the neural network
used, obtaining an update of the failure margins characteristic of the neural network for each specific classified category. On the portal the operation can be repeated an unlimited number of times by each user.

# Developed System
The portal was developed in its front-end and back-end components. For the latter component, it was necessary to design and realise the underlying database which, responding to criteria of generality, was conducted so as to realise a reusable and expandable structure, avoiding specialisations.  
This phase consisted of:
- Conceptual Design, characterised by the creation of the conceptual schema and its documentation through the use of the Entity-Relation model, the adoption of a mixed design strategy and the application of design patterns;
- Logical Design, which required the application of restructuring mechanisms (analysis
redundancy analysis, choice of main identifiers) and translation, concluded with the verification of adherence to normal forms(Boyce-Codd), according to the normalisation theory.
We then proceeded to create the database, the various
relations and the triggers to satisfy the identified rules (minimum cardinality of the relations and updating the performance of the neural networks).
Both the creation of the back-end and front-end components required the application of languages for the creation of static and dynamic web pages (HTML, CSS and JavaScript). Specifically for the realisation of the front-end component, the design templates based on HTML, CSS and JavaScript extensions provided by the **Bootstrap framework** have been used. For the realisation of the back-end component, the support offered by the
**Django framework** structured for the development of applications according to the *'Model-Template-View'* paradigm have been employed. The Python language was adopted both in the realisation of the back-end and in the management of the
image analysis services based on neural networks, as well as for the integration of the latter.


The positive impact of this product in the contemporary technical scenario is justified for two reasons. The first is purely utilitarian and depends on the value of the portal which,
having crossed the threshold of a 'playful' use by non-experts, is configured as a tool for testing the effectiveness and reliability of neural networks, monitoring the accuracy of the results obtained in relation to the selected threshold value. The second aspect is to be found both in the use of particularly popular and cutting-edge software technologies,
as much as in the potential that the portal offers, even to less experienced users, to
reflect on the contributions to innovation made by artificial intelligence.

## Repository structure
- `TSW21_04/`: contains all the code to run the portal;
- `Report and Presentation/`: contains the thesis, abstract and presentation of the members who collaborated on this project, each of whom verticalised his/her work on a specific macrocategory.

## How to run
- Make sure you comply with the installations listed in the related section within the [Read-me.txt file](TSW21_04/Read-me.txt).
- Create a database on the PostgreSQL system called *'IC'* with administrator *'www'* and password *'tsw2021'*:
- On pgAdmin for the created database, execute:
	- the tables creation script [`creazionedb.sql`](TSW21_04/creazionedb.sql)
 	- the trigger creation script [`trigger_prestazioni.sql`](TSW21_04/trigger_prestazioni.sql)
- Move in the prompt to the folder `IC_dj/`, obtained extracting the *.zip* file. When finished, without closing the prompt, run: 

    ```py manage.py makemigrations```

    ```py manage.py migrate ImageClassifier --fake```

    ```py manage.py migrate```

    and, inserting required values, run:
    
    ```py manage.py createsuperuser```
- On pgAdmin execute the populating database script [`popolamento.sql`](TSW21_04/popolamento.sql)
- In the prompt used before, run: 

    ```py manage.py runserver```
- To visualize the portal it is necessary to digit on the browser the address: ```localhost:8000/ImageClassifier/Homepage```

- It is possible to access to admin section using the URL:      ```http://localhost:8000/admin/```, entering with the superuser profile previously created.

In subsequent accesses to the portal, after configuring it as described above, it is possible to open it and run the server by double-clicking on [`AvviaconChrome.bat`](TSW21_04/IC_dj/AvviaconChrome.bat) or [`AvviaconEdge.bat`](TSW21_04/IC_dj/AvviaconEdge.bat)

DEMO
[Here](https://www.youtube.com/playlist?list=PLVKg_HkLrI9FmBmnSPAewnJKdnxcu7r2n) it is possible to see a demo of the developed system and all the implemented features.

Feedback
For any feedback, questions or inquiries, please contact the project maintainers listed in the Contributors section.
