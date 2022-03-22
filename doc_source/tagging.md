# Tagging resources in Amazon Connect<a name="tagging"></a>

A *tag* is a custom metadata label that you can add to a resource in order to make it easier to identify, organize, and find in a search\. Tags are comprised of two individual parts: A tag key and a tag value\. This is referred to as a key:value pair\.

A *tag key* typically represents a larger category, while a tag value represents a subset of that category\. For example you could have *tag key=Color *and *tag value=Blue*, which would produce the key:value pair `Color:Blue`\. Note that you can set the value of a tag to an empty string, but you can't set the value of a tag to null\. Omitting the tag value is the same as using an empty string\.

**Tip**  
AWS Billing and Cost Management can use tags to separate your bills into dynamic categories\. For example, if you add tags to represent different departments within your company, such as `Department:Sales` or `Department:Legal`, AWS can provide you with your cost distribution per department\.



Tag keys can be up to 128 characters in length and tag values can be up to 256 characters in length; both are case sensitive\. For more information, see:
+  [Amazon Connect TagResource](https://docs.aws.amazon.com/connect/latest/APIReference/API_TagResource.html)
+  [Amazon Connect Customer Profiles TagResource](https://docs.aws.amazon.com/customerprofiles/latest/APIReference/API_TagResource.html) 
+  [Amazon Connect Voice ID TagResource](https://docs.aws.amazon.com/voiceid/latest/APIReference/API_TagResource.html): You can add tags to the Voice ID domain\. 
+  [Amazon AppIntegrations TagResource](https://docs.aws.amazon.com/appintegrations/latest/APIReference/API_TagResource.html) 

Amazon Connect services support up to 50 tags per resource\. For a given resource, each tag key must be unique with only one value\. 

**Note**  
Your tags cannot begin with `aws:` because AWS reserves this prefix for system\-generated tags\. You cannot add, modify, or delete `aws:*` tags, and they don't count against your tags\-per\-resource limit\.

To learn more about tagging, including best practices, see [Tagging AWS resources](https://docs.aws.amazon.com/general/latest/gr/aws_tagging.html) in the *AWS General Reference*\. 

## Tag\-based access control<a name="tagging-access-control"></a>

To use tags to control access to resources within your AWS accounts, you need to provide tag information in the condition element of an IAM policy\. For example, to control access to your Voice ID domain based on the tags you've assigned to it, use the `aws:ResourceTag/key-name` condition key to specify which tag key:value pair must be attached to the domain, in order to allow given actions for it\.

For more detailed information on tag\-based access control, see [Controlling access to AWS resources using tags](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_tags.html) in the *IAM User Guide* 