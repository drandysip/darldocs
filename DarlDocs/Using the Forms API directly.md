Using the Forms API directly
===

You can call the underlying DARL API directly for functionality outside of Logic Apps or Azure.

You can see the calls [here](https://darlinf.portal.azure-api.net/docs/services/558ac66cfdc98312f078a65b/operations/558ac66dfdc9830d303b11d3). 

For a forms display of some kind there are three calls you need described here:

[QSet_Get](https://darlinf.portal.azure-api.net/docs/services/558ac66cfdc98312f078a65b/operations/558ac66dfdc9830d303b11d2) which opens the initial form conversation,
[QSet_Post](https://darlinf.portal.azure-api.net/docs/services/558ac66cfdc98312f078a65b/operations/558ac66dfdc9830d303b11d5) which exchanges data with the conversation and
[QSet_Delete](https://darlinf.portal.azure-api.net/docs/services/558ac66cfdc98312f078a65b/operations/558ac66dfdc9830d303b11d4) which acts as a "back" button.
