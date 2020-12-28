# ALB
Application load balancer.

---
AWSTemplateFormatVersion: '2010-09-09'
Description: 'Creating an application load balancer'
Resources:
  Alb:
    Type: 'AWS::CloudFormation::Stack'
    Properties:
      Parameters:
        VpcModule: !GetAtt 'Vpc.Outputs.StackName' # required
        AlertingModule: '' # optional
        BucketModule: '' # optional
        Scheme: 'internet-facing' # optional
        IdleTimeoutInSeconds: '60' # optional
      TemplateURL: './cfn-templates/alb/module.yml'
```

## Parameters

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Default</th>
      <th>Required?</th>
      <th>Allowed values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>VpcModule</td>
      <td>Stack name of vpc module</td>
      <td></td>
      <td>yes</td>
      <td></td>
    </tr>
    <tr>
      <td>AlertingModule</td>
      <td>Stack name of alerting module</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>BucketModule</td>
      <td>Stack name of S3 bucket module</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>Scheme</td>
      <td>Indicates whether the load balancer reachable from the public Internet or only from within the VPC</td>
      <td>internet-facing</td>
      <td>no</td>
      <td>[internet-facing, internal]</td>
    </tr>
    <tr>
      <td>IdleTimeoutInSeconds</td>
      <td>The idle timeout value, in seconds</td>
      <td>60</td>
      <td>no</td>
      <td>1-4000</td>
    </tr>
  </tbody>
</table>
