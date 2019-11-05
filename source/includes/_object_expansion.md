
## Expanding Response Objects


As you interact with Lycan API you may notice that some fields are not included with the response. We do this to keep the response objets lean, and to reduce load/stress for both requester and our servers. As you view different API endpoints you will notice that some will have the "expand" parameter and a set of comma separate values which you can use to expose those values in with the response. If you do not expand the field, you will not see any reference to that attribute/object in the response, allowing you to keep responses from our server lightweight and fast.

A straightforward example of this in practice can be seen in the `/api/channels/:channelId/listings` endpoint. What you will observe is that on some requests you might want the entire `schemaObject` to be exposed on the request, whereas on occassion you may want just the listing IDs without the extra bulk. 

In order to expose these additional fields, you can append a simple GET parameter with the field you are wanting to expand and expose in the response. For example, you would request the API using `/api/channels/:channelId/listings?expand=schemaObject` to receive all listing schema data. If you want to expand multiple fields you can separate them with a comma, such as `?expand=schemaObject,inboundProvider,outboundProvider`. 

<img src="https://www.lucidchart.com/publicSegments/view/c2a205be-7cc0-4378-8278-1969730301ad/image.png" class="img-responsive" />
