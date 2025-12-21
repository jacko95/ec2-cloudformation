# ec2-cloudformation

**Template CloudFormation per il deploy di un'istanza EC2 su AWS**

Questo repository contiene un template AWS CloudFormation per creare e configurare un'istanza EC2.

### Contenuti principali

- `ec2-cf.yaml` — Template CloudFormation principale per il provisioning di un'istanza EC2 (con parametri per tipo istanza, AMI, security group, key pair, ecc.)

### Linguaggi

- YAML (100% – template CloudFormation)

### Prerequisiti

- Account AWS con permessi per CloudFormation e EC2
- AWS CLI configurata (opzionale, per deploy da terminale)

### Utilizzo

1. **Deploy da console AWS**:
   - Vai su AWS CloudFormation > Create stack
   - Carica il file `ec2-cf.yaml`
   - Configura i parametri richiesti (es. InstanceType, KeyName, ImageId, ecc.)

2. **Deploy con AWS CLI**:
   ```bash
   aws cloudformation create-stack \
     --stack-name mia-ec2-stack \
     --template-body file://ec2-cf.yaml \
     --parameters ParameterKey=InstanceType,ParameterValue=t3.micro \
                  ParameterKey=KeyName,ParameterValue=la-tua-key-pair \
                  ParameterKey=ImageId,ParameterValue=ami-12345678
