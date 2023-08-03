# ansible-cac-workshop-solutions
Solutions to the CAC workshop found here: 
https://aap2.demoredhat.com/exercises/ansible_config_as_code/


Notes about workshop:

1. Exercise 0 can be skipped to speed up and avoid linting issues - especially with profile prod
2. When creating the vault file, the password value for ah_token_password needs to be 9 chars minimum to avoif failures - so set to generated pass twice
3. When creating credential types, the extra vars and the env variables need an !unsafe before the var mappings 
4. in the controller config playbook, the following var should be set at the play level as a workaround for an issue with the image:

```yaml
   controller_configuration_async_dir: '/tmp/.ansible_async'
```
