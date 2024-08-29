## About GenAI SmartReminder PM Assistant
Redefining the future of work with GenAI and Automation!

This custom intelligent application sends dynamic reminders to team members, ensuring essential tasks like code check-ins, updates, and follow-ups are completed without a hitch. The toole enables PM to make daily project management tasks seamless and stress free

By using Generative AI, each reminder is thoughtfully rephrased, keeping the messages engaging and preventing them from becoming repetitive. This approach is making both managers and team members happier—managers save valuable time, and team members appreciate the gentle, non-intrusive prompts.

### Pre-requisites
- A Power Automate Premium License
- A Dataverse License (Power Apps Per User Plan will work too)
- Teams Services assigned to the account that will host this workflow
- AI Prompt

### Create a Dataverse Table

Go to https://make.powerapps.com/ >> Tables >> New Table >> Start with Blank Table >> Add columns as given below >> Rename Table to EmployeesGroup

Create a custom table in Dataverse. Refer to the details given in the below table to create columns.

![image](https://github.com/user-attachments/assets/b898a340-72ec-4201-aede-b0b81cdbb33c)

### Make a Prompt
Go to https://make.powerautomate.com/

Click on More >> Discover all >> AI >> AI Prompts

![image](https://github.com/user-attachments/assets/fa1c4407-210c-4ff6-8a32-10f3e4761e76)

![image](https://github.com/user-attachments/assets/e15d1fb4-52fd-431f-8745-7d2e504b472d)

Click on Create text with GPT using a prompt >> Add inputs >> Add your Dataverse table >> Configure your prompt >> Rename your prompt >> Save your custom prompt.

![image](https://github.com/user-attachments/assets/48b9262b-adcd-4b01-86bb-780ddbb2fc14)

![image](https://github.com/user-attachments/assets/11da99ed-3db0-4a77-9a2b-145effb4ad64)

![image](https://github.com/user-attachments/assets/3ba61afd-0494-46ff-87ed-289a3cb653a5)

You can use the following prompt or add your own. Once you added a prompt click on Save Custom prompt

``` Please generate a message to be a friendly and informal tone reminder for. for Role  
Follow the instructions:
- Only keep the message body as the response.
- Learn from Variations marked in triple quotes
- Message should remind the programmers to check in their code on GitHub
- Message should also remind programmers to keep all/any team member updated on any dependencies
- Message should also remind put out a status update on client CR/Tickets to team members/clients
- User greetings at the start and end
- Add a '*' prefix to the End greeting.
- list out reminders using '#'

Output Format:
[Opening greetings]
 # [Reminder 1]
 # [Reminder 2]
 # [Reminder 3] 
*[Ending greetings(without names)]
```

### Import Power Automate Flow

Go to https://make.powerautomate.com/

Click on Import in My Flows sections

![image](https://github.com/user-attachments/assets/8cd19ec5-bf68-4fbc-9ada-579e3714b9a4)

![image](https://github.com/user-attachments/assets/9499ec30-e0a3-476e-bb04-25dde2d130a7)

Import DailyTasksReminder zip package

![image](https://github.com/user-attachments/assets/da552476-9d86-4851-9fc0-770ae12ee99a)

Wait till the package is uploaded, then make sure the import setup is set as create as new. Add your connections to Dataverse and Teams. Then click on import

![image](https://github.com/user-attachments/assets/3a2aaa5f-7dc8-4112-8660-7e8de4c4e210)

Once flow is successfully imported. You will see a message shown in the image below. Click on Open flow.

![image](https://github.com/user-attachments/assets/ecc01081-f1ad-4736-90f7-8f90d66adb6e)

Make sure that the List Rows action uses your Dataverse table. And then click on Save.

![image](https://github.com/user-attachments/assets/2d5e6504-eaf1-4827-bb04-ba446a8a87a7)

After saving the flow make sure you turn the flow on

![image](https://github.com/user-attachments/assets/5ff5dba8-ff09-489b-9010-563ea436f774)

## Notes:
- AI Prompt only supports the Dataverse table
- You can customize your prompts according to your requirements
- The flow is set(trigger) to run between 4 - 4:30 PM IST, Monday to Friday. You can change that in the trigger

