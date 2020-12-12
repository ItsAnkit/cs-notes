Smarter version of rest API to handle over and under cutting of data obtained from resource.

A GraphQL type consists of fields and arguments. It defines following types:

>>> Query and Mutation types
    Every GraphQL service has a query type and may or may not have a mutation type.

>>> Object types
    These represent the objects you can fetch from a GraphQL service and the fields each object holds.

>>> Scalar types
    These are default types like Float, Int, String, Boolean.

>>> Enumeration types

>>> Input types
	Object types passed as arguments to queries.

* Other types include Union, List, Non-Null, and Interface.

>>> Subscription
    Sends changes to clients in real-time

>>> GraphQL::Schema::Resolver 
	class is a container that can hold logic belonging to a field
