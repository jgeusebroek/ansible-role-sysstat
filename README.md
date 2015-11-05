# Ansible role: sysstat

An Ansible Role that installs and configures the sysstat performance monitoring tools RedHat/CentOS or Debian/Ubuntu.

## Requirements

None

## Dependencies

None

## Example Playbook

    ---
    - hosts: all
      sudo: yes

      roles:
         - { role: jgeusebroek.sysstat, tags: ["sysstat"] }

## Example Variables

	# How long to keep log files (in days).
	# Used by sa2(8) script
	# If value is greater than 28, then log files are kept in
	# multiple directories, one for each month.
	sysstat_history_days: '28'

	# Compress (using gzip or bzip2) sa and sar files older than (in days):
	sysstat_compress_days: '10'

	# Parameters for the system activity data collector (see sadc(8) manual page)
	# which are used for the generation of log files.
	# By default contains the `-S DISK' option responsible for generating disk
	# statisitcs. Use `-S XALL' to collect all available statistics.
	sysstat_options: '-S DISK'

	# Compression program to use.
	sysstat_compression_program: 'bzip2'

## License

MIT / BSD

## Author Information

This role was created in 2015 by [Jeroen Geusebroek](http://jeroengeusebroek.nl/).