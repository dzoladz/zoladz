"Beam Me Up, Scotty!" is a presentation for the [Ohio Library Council's](http://olc.org/) event, [RightClick 2017](http://olc.org/rightclick/), at the [State Library of Ohio](https://library.ohio.gov/). RightClick 2017 is an annual one-day conference for sharing IT ideas, solutions, and best practices by and for library IT staff and administrators. 

You can view the [RightClick 2017 presentation](https://dzoladz.github.io/rightclick2017/), if you'd like.


## reveal.js

Slides are built upon [reveal.js](https://github.com/hakimel/reveal.js). There is a [demo](http://lab.hakim.se/reveal-js/#/) available.

#### Local Development

1. Navigate to `/path/to/rightclick2017`. Serve the presentation and monitor source files for changes.
   ```sh
   $ npm start
   ```

1. Open <http://localhost:8000> to view your presentation

#### Navigate 

- <kbd>f</kbd>: Fullscreen
- <kbd>ESC</kbd>: Show slide explorer / Exit fullscreen
- <kbd>s</kbd>: View speaker notes
- <kbd>.</kbd>: Pause
- <kbd>?</kbd>: Show keyboard shortcuts

## Evergreen: Test Server Build

The following procedure takes advantage of the Ansible work of Bill Erickson, King County Library System.

You'll need to have a server running Ubuntu 16.04 LTS. I've got this running on a local VM on VirtualBox to experiment with making aesthetic changes or to explore new features in each release. You'll need to allocate about 4GB of RAM to the machine.

Using the auto-installer script, services should only be listening on 127.0.0.1 by default. Assuming you establish a sane firewall configuration, you could also deploy this to Amazon EC2, Microsoft Azure, or Google Cloud Platfrom. One caveat to doing so, the auto-installer essentially follows the procedures for installing and configuring OpenSRF and Evergreen from the Evergreen-ILS website. As such, they use well-known passwords for the Ejabberd and Postgres accounts. This should not be a huge concern by itself. The script also sets Evergreen to use Rsyslog and NGINX, but the community instruction do not. These settings and passwords can be changed in settings.yml.

#### Install Git and Ansible
```bash
sudo apt-get install git ansible
```
#### Clone
```bash
git clone --branch collab/berick/ansible-installer-ubuntu-16.04  git://git.evergreen-ils.org/working/random.git
```
#### Change to `/random` directory
```bash
cd random
```
#### Run
```bash
sudo ansible-playbook playbook.yml -e "hosts=127.0.0.1"
```
In Chrome, or Firefox, navigate to `https://<HOSTNAME>/eg/staff/` and click through the SSL warning to access the staff client.

## Further Exploration

#### Consortium of Ohio Libraries
- Consortium of Ohio Libraries [Website](http://info.cool-cat.org/)
- COOL-CAT [Consortial Catalog](http://cool-cat.org/eg/opac/home)

#### Documentation
- Evergreen: Database Schema [master](http://docs.evergreen-ils.org/dev/schema/)
- Evergreen: System Configuration and Customization [HTML](http://docs.evergreen-ils.org/3.0/_system_configuration_and_customization.html)

#### Tools
There are so many possible tools that it's laughable to create a list. For the sake of providing some potentials, here you go:
- Equinox Migration Tools 
```bash
git clone git://git.esilibrary.com/migration-tools.git
```
- pymarc [GitHub](https://github.com/edsu/pymarc)

#### Presentations
- Jason Etheridge, Staging Migrations for Success [Slides](http://tinyurl.com/EGmigrations2)
- The Usual Suspects (De-duplication Methods in Evergreen) [Slides](https://goo.gl/kKf1AO)