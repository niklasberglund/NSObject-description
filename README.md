# NSObject-description
Helps you produce `description` method output formatted same way as Apple's classes' `description` output.

# Install
Either manually add the files to your project or install using CocoaPods. Add NSObject+description to your Podfile like so:
```
pod 'NSObject+description'
```

# Usage

## Manually pass attribute names and values
Override the class' `- (NSString *)description` method to have it return the *NSString* produced by `- (NSString *)descriptionWithMembers:`. Pass a *NSDictionary* with names and values of your object's attributes to `descriptionWithMembers:` like so:

```
- (NSString *)description
{
	return [self descriptionWithMembers: @{
		@"firstName:": self.firstName,
		@"lastName": self.lastName,
		@"phoneNumber": phoneNumber
	}];
}
```

## Automatically fetch attributes
You can have your `- (NSString *)description` method return a *NSString* representation of your class without manually passing the attributes manually like so:
 
```
- (NSString *)description
{
	return [self descriptionWithAllProperties];
}
```

