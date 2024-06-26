### Verify Pod Labels
``` kubectl get pods --show-labels ```

### Check other policies 
``` kubectl get ciliumnetworkpolicies ```

### Use debug utility 
``` exec -ti cilium-bjjfh -n cilium -- /bin/bash ```
