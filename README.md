# Swift-JsonSerializer

A pure-Swift JSON parser and serializer. It has been modified to work as a Swift package (See https://swift.org/package-manager/ for more info).

# SYNOPSIS

```
import SwiftJsonSerializer

// Get a json string into a object (dictionary)
let string = "{\"first_name\": \"Jim\", \"last_name\": \"Smith\"}"
let data = string.dataUsingEncoding(NSUTF8StringEncoding, allowLossyConversion: true)!

do {
  let object = try Json.deserialize(data)
  print("object: \(object)")
} catch {
  print("Json deserialize error: \(error)")
}

// build a JSON structure
let profile: Json = [
  "name": "Swift",
  "started": 2014,
  "keywords": ["OOP", "functional programming", "static types", "iOS"],
]
print(profile.description)      // packed JSON string
print(profile.debugDescription) // pretty JSON string
```

# DESCRIPTION

Swift-JsonSerializer is a JSON serializer and deserializer which are implemented in **pure Swift** and adds nothing
to built-in / standard classes in Swift.

# KNOWN ISSUES

* This library doesn't work with optimization flags (`swiftc -O`) as of Xcode 6.1.1 / Swift version 1.1 (swift-600.0.56.1).

# SEE ALSO

* [RFC 7159  The JavaScript Object Notation (JSON) Data Interchange Format](http://tools.ietf.org/html/rfc7159)

# AUTHOR

Fuji, Goro (gfx) gfuji@cpan.org

# LICENSE

The Apache 2.0 License
