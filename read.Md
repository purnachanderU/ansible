Marker	
|	literal — keeps newlines
|-	literal, strip the trailing newline
|+	literal, keep all trailing newlines
>	folded — newlines become spaces (one long line)
>-	folded, strip trailing newline

###########################
YAML literal block scalar. It keeps newlines exactly as written, which is what you want for a multi-line msg.
example:  here | is multiline 
msg: |
  OS Family : {{ ansible_facts['os_family'] }}
  private_ip: {{ ansible_facts['default_ipv4']['address'] }}

msg: |
  line one
  line two
# => "line one\nline two\n"

msg: >
  line one
  line two
# => "line one line two\n"

Ansible has no print module. ansible.builtin.debug is the standard way to print output to the console


