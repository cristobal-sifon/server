``selknam`` information sheet
=========================

Specs
-----

``selknam`` contains 2 Intel(R) Xeon(R) Silver 4210 CPUs @ 2.20GHz each with 10 cores and 2 threads per core and 512 GB DDR4 RAM. Total disk space is roughly 45 TB. Limited backup space is available upon request, but *data are not backed up automatically*. It also has one NVIDIA QUADRO P5000 GPU with 3072 CUDA cores and 16GB GDDR5 RAM.

Obtaining access
----------------

To obtain access to ``selknam``, send the **public** ssh key of the computer you want to connect from via e-mail, together with your preferred user name. If you do not have a key, type the following on a terminal: ::

	ssh-keygen -t rsa

Follow the prompts (just press ``Enter`` a few times). Once finished you will have two new files: ::

	~/.ssh/id_rsa
	~/.ssh/id_rsa.pub

The ``.pub`` file contains the public key, which you are free to share to allow connections to any number of servers wherever they may be. **Never, under any circumstances, share the private key.** If you believe the private key might have been compromised, please notify us immediately and send a new public key.

Connecting
----------

Upon confirmation you will be given the port required to access; go to ``~/.ssh/config`` and type at the end ::

	Host selknam.fis.ucv.cl
		Port xxxx

Replacing ``xxxx`` with the number given. Open a new terminal and you will be allowed to connect: ::

	ssh -X <user>@selknam.fis.ucv.cl

Each user owns two directories:

* ``/home/<user>`` has a user quota of 1 GB and should therefore only be used for minimal configurations and light-weight software. This folder and all its subdirectories are hidden from other users' view.

* ``/data2/<user>`` has a user quota of 1 TB; more space may be requested with justification. Users should store all their data and code here. Other users have read-only access to the contents of this folder. You may change this configuration if you wish, but you do it at your own risk.

For easy data access, we recommend mounting your ``selknam`` directory on your local machine with ::

	sshfs <user>@selknam.fis.ucv.cl:/data2/<user> <dir>

where ``<dir>`` is a directory on your own computer. When you've finished working with ``selknam``, you should unmount it: ::

	fusermount -u <dir>

Software
--------

``conda`` is installed and activated by default. When possible, installing software with ``conda install`` is recommended. Some  astronomical and related software (e.g., ds9, topcat) are installed by default. Other minor software may be installed on the user's directories. If particular software requires system-wide installation or root privileges, please contact us explaining the situation.

**DisPerSE:** ``selknam`` has a dedicated ``DisPerSE`` conda environment available to all users, which may be activated by typing ::

	conda activate disperse	

Data
----

The following public  data are available as read-only to all users:

.. list-table::
	:header-rows: 1

	* - Directory
	  - Content
	  - References or acknowledgements
    * - ``/data2/decals/``
      - DECaLS DR9, DR10, and DR10.1 sweeps and photometric redshift sweeps (except DR10)
      - See `Legacy Survey <https://www.legacysurvey.org/decamls/>`_ for latest information and `here <https://www.legacysurvey.org/acknowledgment/>`_ for acknowledgements.
    * - ``/data2/act/dr4``
      - ACT DR4 component-separated maps
      - `Madhavacheril et al. (2020) <https://ui.adsabs.harvard.edu/abs/2020PhRvD.102b3534M/abstract>`_
    * - ``/data2/act/dr6``
      - ACT DR6 component-separated maps
      - `Coulton et al. 2024 <https://ui.adsabs.harvard.edu/abs/2024PhRvD.109f3530C/abstract>`_


Acknowledgements
----------------

If you use ``selknam`` in your research, please include the following acknowledgement: �"[Initials] acknowledges support from Agencia Nacional de Investigaci\'on y Desarrollo (ANID) through FONDECYT grant no. 11191125".


Contact
-------

For all inquiries please contact Cristóbal Sifón at ``cristobal.sifon`` at ``pucv.cl``.
