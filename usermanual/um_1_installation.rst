.. sectionauthor:: Jonathon Love

Installation
============


Windows
-------

<<<<<<< HEAD
   jamovi is available for Windows Vista (64-bit) and above. Installation on windows is quite straight-forward, and should be familiar to anyone who has
   installed software on Windows before. Download the latest version from the `download page <https://www.jamovi.org/download.html>`__, and double-click the
   icon.

   At some institutions (particularly universities), the “normal” approach to installing software is blocked by IT security policies. In this case, you can
   download our ``.zip``-version. To use this, simply download, unzip to a location on the computer, and naviagate to the bin folder. Double-clicking
   ``jamovi.exe`` will begin jamovi. It’s possible that additional security restrictions prevent jamovi from working in this way, in which case it would be
   worth raising the issue with your IT staff.
=======
   jamovi is available for Windows Vista (64-bit) and above.
   Installation on windows is quite straight-forward, and should be
   familiar to anyone who has installed software on Windows before.
   Download the latest version from the `download
   page <https://www.jamovi.org/download.html>`__, and double-click the
   icon.

   At some institutions (particularly universities), the “normal”
   approach to installing software is blocked by IT security policies.
   In this case, you can download our .zip version. To use this, simply
   download, unzip to a location on the computer, and naviagate to the
   bin folder. Double-clicking jamovi.exe will begin jamovi. It’s
   possible that additional security restrictions prevent jamovi from
   working in this way, in which case it would be worth raising the
   issue with your IT staff.
>>>>>>> master


macOS
-----

<<<<<<< HEAD
   jamovi is available for macOS 10.9+ (Mavericks and newer). To install it, download the ``.dmg``-file from our `download page
   <https://www.jamovi.org/download.html>`__, and double-click the downloaded file. This will present you with a “file view”, and you can install jamovi by
   “dragging-and-dropping” the jamovi application to the Applications folder (in the usual way). After this, jamovi will appear in your applications, and can
   be started like any other installed application.

   jamovi for macOS has an auto-update mechanism, and can alert you to when new versions are available. You can update your version of jamovi from the app menu
   (☰; at the top right of the window).
=======
   jamovi is available for macOS 10.9+ (Mavericks and newer). To install
   it, download the .dmg file from our `download
   page <https://www.jamovi.org/download.html>`__, and double-click the
   downloaded file. This will present you with a “file view”, and you
   can install jamovi by “dragging-and-dropping” the jamovi application
   to the Applications folder (in the usual way). After this, jamovi
   will appear in your applications, and can be started like any other
   installed application.

   jamovi for macOS has an auto-update mechanism, and can alert you to
   when new versions are available. You can update your version of
   jamovi from the app menu (☰; at the top right of the window).
>>>>>>> master


Linux and Chromebooks
---------------------

<<<<<<< HEAD
   jamovi is currently available for Linux, (for all ‘flatpak participating linux distributions’ – which is most of them), and Chromebooks, from flathub.

   **Note**: Some Chromebooks experience a blank screen issue when starting up jamovi. If you encounter this, there are instructions on how to fix this a
   little :ref:`further down<blank-screen-on-chromebooks>`.

   If you’re new to flatpak/flathub, you’ll need to follow the setup guide on `our flathub page <https://flathub.org/apps/details/org.jamovi.jamovi>`__.

   If you’re an old hand at flatpak, you can install jamovi with the command:
=======
   jamovi is currently available for Linux, (for all ‘flatpak
   participating linux distributions’ – which is most of them), and
   Chromebooks, from flathub.

   **Note**: Some Chromebooks experience a blank screen issue when
   starting up jamovi. If you encounter this, there are instructions on
   how to fix this a little :ref:`further down<blank-screen-on-chromebooks>`.

   If you’re new to flatpak/flathub, you’ll need to follow the setup
   guide on `our flathub page
   <https://flathub.org/apps/details/org.jamovi.jamovi>`__.

   If you’re an old hand at flatpak, you can install jamovi with the
   command:
>>>>>>> master

   .. code-block:: bash
   
      flatpak install flathub org.jamovi.jamovi

   and later, you can update your version of jamovi with:

   .. code-block:: bash
   
      flatpak update


Text not appearing in plots under linux
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<<<<<<< HEAD
   On some linux machines, the flatpak font cache is not up-to-date, resulting in plots in jamovi not displaying text correctly. To remedy this, you can run
   the following command at the terminal:
=======
   On some linux machines, the flatpak font cache is not up-to-date,
   resulting in plots in jamovi not displaying text correctly. To remedy
   this, you can run the following command at the terminal:
>>>>>>> master

   .. code-block:: bash
   
      flatpak run --command=fc-cache org.jamovi.jamovi -f -v

<<<<<<< HEAD
   This appears to be an issue with flatpaks, and we’re working with the flatpak community to get to the bottom of it.
=======
   This appears to be an issue with flatpaks, and we’re working with the
   flatpak community to get to the bottom of it.
>>>>>>> master

.. _blank-screen-on-chromebooks:

Blank screen at startup on Chromebooks
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<<<<<<< HEAD
   Some Chromebooks experience a blank screen when starting up jamovi. The cause of this issue is not completely clear at this time, however it can be fixed by
   disabling “Crostini GPU support”.

   Enter ``chrome://flags/`` into the ChromeOS address bar. This will bring up “Experiments”. Search for ``Crostini GPU Support`` and set it to disabled. After
   restarting your Chromebook the issue will be fixed (special thanks to `@mulderc <https://github.com/mulderc>`__).
=======
   Some Chromebooks experience a blank screen when starting up jamovi.
   The cause of this issue is not completely clear at this time, however
   it can be fixed by disabling “Crostini GPU support”.

   Enter ``chrome://flags/`` into the ChromeOS address bar. This will
   bring up “Experiments”. Search for ``Crostini GPU Support`` and set
   it to disabled. After restarting your Chromebook the issue will be
   fixed (special thanks to `@mulderc <https://github.com/mulderc>`__).
>>>>>>> master
