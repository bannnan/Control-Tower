## Enable un-supported regions for AWS Control Tower

1. Disable SCP on the AWS Organization.

    ![image](https://user-images.githubusercontent.com/62671936/172653473-61c38b79-9002-4eaa-b449-a443a054f30d.png)


2. Get the Parameters used for both “BASELINE-CONFIG, and BASELINE-CLOUDWATCH CFTs” in any of the supported regions. Example (eu-west-1).

    ![image](https://user-images.githubusercontent.com/62671936/172656970-bc345f28-0305-479e-a1c3-8c5f04fcaa4e.png)

3. Clone the Control Tower repository.

5. Open the control-tower-1.yml file and add the region you want to enable on line 164 and save it.

    ![image](https://user-images.githubusercontent.com/62671936/172652519-7e0bfc3f-8469-4826-a6de-97bf6f9bd828.png)

 

5. Go to Amazon CloudFormation in the unsupported region. Example: me-south-1 and run the two CloudFormation templates. Fill out the parameters using the data captured in Step 2.

6. Go to the root account and hit “Repair” in the AWS Control Tower portal. This will take 1 hour to re-enable the SCPs on all accounts.

    ![image](https://user-images.githubusercontent.com/62671936/172652535-f82c14b6-e8da-4695-9f45-95830591c635.png)

7. Now you can use any guardrail enabled on supported regions and manually run the CFT on your unsupported region.

    ![image](https://user-images.githubusercontent.com/62671936/172652555-86ec8004-61ee-47bf-a715-e36fa80eee50.png)
