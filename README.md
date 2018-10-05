NxBRE
=====

[![Build Status](https://travis-ci.org/ddossot/NxBRE.svg?branch=master)](https://travis-ci.org/ddossot/NxBRE)

Web site, knowledge base: http://nxbre.dossot.net


NxBRE2
------

For .NET 1.1 
Developed on SharpDevelop 1.x


NxBRE3
------

Not backwards compatible with NxBRE2

For .NET 2.x
Developed on SharpDevelop 2.x


IE-Console
----------
Based on the mainstream NxBRE version


StressTest
----------
Projects used to stress NxBRE (released for v3)


Misc
----
  Documentation source and other random stuff


Contributing
============
> All contributions are de-facto included under the MIT Licence.

To contribute a new feature or fix:
- Clone this repository under your account,
- Create a branch for the contribution, named `x-${feature_name}` (for example `x-rulelml1.0-support`),
- Commit your changes to this branch,
- When done, consider squashing your commits (optional),
- Then create a pull request towards this repo's master branch.

Thank you for contributing!

#### MIT Licence (c) 2003-2015 - David Dossot <david@dossot.net>


==== ErrCode Addendum begins below ====

Unit Testing Quick Start
------------------------
To get the NUnit test working, either reconfigure the relevant properties in the `NxBRE-UnitTest.dll.config` file for your checkout directory. Initial checkout of the `NxBRE-UnitTest.dll.config` file will look like this:
```
<?xml version="1.0" encoding="utf-8"?>
<configuration>
	<appSettings>
		<add key="nxbre.securitySandbox" value="true"/>
		<!--
			**********
			Unit Tests
			**********
		-->
		<add key="nxbre.unittest.inputfile" value="Q:/test.xbre"/>
		<add key="nxbre.unittest.inputnative" value="Q:/discount.bre"/>
		<add key="nxbre.unittest.identityxsl" value="Q:/identity.xsl"/>
		<add key="nxbre.unittest.ruleml.inputfolder" value="Q:/"/>
		<add key="nxbre.unittest.outputfolder" value="C:/Temp"/>
	</appSettings>
</configuration>
```
Judging by the settings in that config, you can map `Q:` to the `RuleFiles` folder (in Windows via the [`subst` / `net use`](https://superuser.com/a/644706/736459) command) as an alternative to editing the above config file. See the `Configuration` section of documentation (e.g. `NxBRE-Documentation-3_3_0.odt`) for additional info.

You will probably also find that the `nunit-framework` reference is broken. To fix this add the `Nunit` NuGet package and specifically install version 2.7.0 (NUnit v3.0.0 and newer were found to be incompatible with the unit tests as they were written for v2).

Also if you're using a newer version of Visual Studio (e.g. VS 2017), you'll find that VS's built-in `Test Explorer` will not be able to run the tests unless you also add the `NUnitTestAdaptor` NuGet package (v2.1.1 seems to work fine with NUnit v2.7.0). Once done, you should be able to run the unit tests from within VS.
