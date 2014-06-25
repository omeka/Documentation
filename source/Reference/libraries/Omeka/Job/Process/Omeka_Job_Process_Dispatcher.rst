----------------------------
Omeka_Job_Process_Dispatcher
----------------------------

Package: :doc:`Job\\Process </Reference/packages/Job/Process/index>`

.. php:class:: Omeka_Job_Process_Dispatcher

    Spawns and manages background processes.

    .. php:method:: startProcess($className, $user = null, $args = null)

        Create a table entry for a new background process and spawn it.

        :type $className: string
        :param $className: Omeka_Job_Process_AbstractProcess subclass name to spawn
        :type $user: User
        :param $user: User to run process as, defaults to current user
        :type $args: Array|null
        :param $args: Arguments specific to the child class process
        :returns: Process The model object for the background process

    .. php:method:: stopProcess(Process $process)

        Stops a background process in progress.

        :type $process: Process
        :param $process: The process to stop.
        :returns: bool True if the process was stopped, false if not.

    .. php:method:: getPHPCliPath()

    .. php:method:: _checkCliPath($cliPath)

        Checks if the configured PHP-CLI path points to a valid PHP binary.
        Flash an appropriate error if the path is invalid.

        :param $cliPath:

    .. php:method:: _autodetectCliPath()

    .. php:method:: _getBootstrapFilePath()

        Returns the path to the background bootstrap script.

        :returns: string Path to bootstrap

    .. php:method:: _fork($command)

        Launch a background process, returning control to the foreground.

        :param $command:
