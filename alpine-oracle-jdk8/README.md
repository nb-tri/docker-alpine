# Alpine 3.8 / Oracle JDK 8.152.16 / Unlimited JCE Policy
This image to help anyone work with Amazon AWS Java SDK client and have the below error:
class not found sun/security/ssl/SupportedEllipticCurvesExtension

The problem is, the build after 152 of JDK8, will remove some classes and affected it.

Thanks simdevmon to explore it from: https://github.com/payara/Payara/issues/2344