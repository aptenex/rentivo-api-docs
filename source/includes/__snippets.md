

<div class="auth-wrapper">
    <button class="btn authorize unlocked">
        <span>Bearer Token</span>
    </button>
</div>



<div class="opwrapper">
    <div class="opblock opblock-post" >
        <div class="opblock-summary opblock-summary-post">
            <span class="opblock-summary-method">POST</span>
            <span class="opblock-summary-path">
                <a class="nostyle">
                    <span>{{entryPoint}}/api/property/:propertyId/listings?expand=channel,provider</span>
                </a>
            </span>
            <div class="opblock-summary-description">
                Get Authentication JWT (Bearer)
            </div>            
        </div>
    </div>
</div>



<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`_username`<br><span class="label notice">Required</span>|Your username
`_password`<br><span class="label notice">Required</span>|Your password
`application_hash`<br><span class="label notice">Required</span>|Your application hash

