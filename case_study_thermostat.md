# Case study: Thermostat

> Some thermostats have built-in web servers.

### Risk
- Turning off someone's heat in the middle of winter?
- Turning on the heat in the summer?
- Run heat and air conditioning simultaneously?

### Vulnerability
- Web server uses `http` other than `https`: 
> 1) handshake encryption on Thermostat might be expensive in terms of CPU; 2) how to update web certificates on Theormostat (company doesn't want users to replace thermostats in every 5 years)?
- Unencrypted traffic from the server to the thermostats.
- The passwords are sent in the clear across the Internet, passwords may be stored in clear in bulk on the server.

### Privacy issues
- Energy consumption pattern
> Turn off thermostats for a long time, then turn on thermostats $$\rightarrow$$ possibly just coming back from vacation.

### Defenses
- Users can't touch thermostat software (As of notes being taken, Dec 2014).
- Add layering by adding VPN, build users' own access control.

> Overall, it's hard to know all the threats. We can see what is made available, and ask who might want it.

> Check "gold standard" (Au): Authentication, Authorization, Audit.



