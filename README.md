## ExpNo 1 :Developing AI Agent with PEAS Description
## NAME : G P HARIESH
## Register number: 212224040100
## AIM

To find the PEAS description for the given AI problem and develop an AI agent.


## THEORY

The AI Exam Invigilator Agent monitors students during an examination to ensure a fair and malpractice-free environment. The agent observes students using sensors such as cameras and detects suspicious activities like using a mobile phone, talking to others, or repeatedly looking away from the answer sheet. Whenever suspicious behavior is detected, the agent alerts the invigilator and records the incident. The performance of the agent increases when it correctly detects suspicious activities and decreases when it has to monitor multiple students continuously. Thus, the agent helps maintain discipline and integrity during examinations.

## DESIGN STEPS:
STEP 1: Identifying the input:
Student activities such as mobile phone usage, talking, and looking away during the examination.

STEP 2: Identifying the output:
Generate a warning or alert if suspicious behaviour is detected; otherwise continue monitoring the students.

STEP 3: Developing the PEAS description:
Develop the PEAS description by identifying the Performance measure, Environment, Actuators, and Sensors of the AI Exam Invigilator Agent.

STEP 4: Implementing the AI agent:
The agent continuously monitors students, detects suspicious activities, alerts the invigilator, and records incidents whenever malpractice is detected.

STEP 5: Measuring the performance parameters:
The performance of the agent is increased for every correctly detected suspicious activity and decreased for continuous monitoring or movement between students.

## PEAS DESCRIPTION:



| Agent Type | Performance | Environment | Actuators | Sensors |
|------------|-------------|-------------|-----------|----------|
| AI Exam Invigilator Agent | Detect suspicious activities, Monitor students, Maintain fair examination | Examination Hall, Students | Display Warning, Alert Invigilator, Record Incident | Camera, Mobile Phone Detection, Talking Detection, Eye Movement |


## PROGRAM:
```
import random

class ExamInvigilatorAgent:
    def __init__(self, exam_data):
        self.exam_data = exam_data

    def monitor_exam(self):
        while True:
            current_exam_state = self.sensors.get_exam_state()

            print("\nCurrent Student Status")
            print(current_exam_state)

            action = self.choose_action(current_exam_state)

            self.actuators.perform_action(action)

            if action == "Student behavior is normal":
                break

    def choose_action(self, current_exam_state):

        if current_exam_state['phone_detected']:
            return "Alert: Mobile phone detected"

        elif current_exam_state['talking']:
            return "Warning: Student is talking"

        elif current_exam_state['looking_away']:
            return "Warning: Student is looking away frequently"

        else:
            return "Student behavior is normal"


class ExamSensors:

    def get_exam_state(self):

        return {
            'phone_detected': random.choice([True, False]),
            'talking': random.choice([True, False]),
            'looking_away': random.choice([True, False])
        }


class ExamActuators:

    def perform_action(self, action):
        print("Action:", action)


if __name__ == "__main__":

    exam_data = {
        'exam_name': 'AI Laboratory',
        'room_no': 'Lab-1'
    }

    exam_sensors = ExamSensors()
    exam_actuators = ExamActuators()

    exam_agent = ExamInvigilatorAgent(exam_data)

    exam_agent.sensors = exam_sensors
    exam_agent.actuators = exam_actuators

    exam_agent.monitor_exam()

```
## OUTPUT
<img width="596" height="761" alt="image" src="https://github.com/user-attachments/assets/c0f4d2e2-b77a-489a-8f62-fe4630e85de7" />


## RESULT:

Thus the Developing AI Agent with PEAS Description was implemented using python programming.
