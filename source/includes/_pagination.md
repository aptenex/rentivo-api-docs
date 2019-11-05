# Pagination

Endpoints which enumerate objects support page based pagination.

##### Request arguments

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`page`<br><span class="label">Optional</span>|Determine which page, offset starting from 1, for which your response shall return
`count`<br><span class="label">Optional</span>|Determine how many results shall be returned in the response. The default is 100. Please be aware that Lycan will return a gateway error if you request too many results. <br /> This is by design. Because on some endpoints we allow you to expand relationships, it is advisable that you use lower count sizes for larger document sizes to avoid API requests being dropped.

