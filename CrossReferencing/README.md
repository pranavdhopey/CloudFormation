This CloudFormation Stack will demonstrate how to create cross-stack reference i.e to reference a resource in AWS CloudFormation stack to Other stack.

In this example we will create EC2Stack with two EC2 instances in two avaialibility zones (ap-south-1a and ap-south-1b) and Export the value of EC2 resources to be referenced as a input to CLBStack, ALBStack and NLBStack.

# EC2Stack Properties:

## Instance1: 
  **AMIId:** ami-04b1ddd35fd71475a 
  **AZ:** ap-south-1a
  **ExportedValue:** MyInstance1
  
## Instance2: 
  **AMIId:** ami-04b1ddd35fd71475a                                                                                                                                                 
  **AZ:** ap-south-1b                                                                                                                                                              
  **ExportedValue:** MyInstance2                                                                                                                                                   
  
## CLBStack Properties
  **ListnerPort:** 80
  **Protocol:** HTTP
  **LB Type:** Classic LoadBalancer - Internet Facing
   
## ALBStack Properties
  **ListnerPort:** 80
  **Protocol:** HTTP
  **LB Type:** Application LoadBalancer - Internet Facing
  
## NLBStack Properties
  **ListnerPort:** 80 
  **Protocol:** TCP
  **LB Type:** Network LoadBalancer - Internet Facing  
