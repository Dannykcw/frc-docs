Get Alliance Color
==================

The ``DriverStation`` class (`Java <https://github.wpilib.org/allwpilib/docs/release/java/edu/wpi/first/wpilibj/DriverStation.html>`__, `C++ <https://github.wpilib.org/allwpilib/docs/release/cpp/classfrc_1_1_driver_station.html>`__, :py:class:`Python <robotpy:wpilib.DriverStation>`) has many useful features for getting data from the Driver Station computer.  One of the most important features is ``getAlliance`` (Java & Python) / ``GetAlliance`` (C++).

Getting your Alliance Color and Doing an Action
-----------------------------------------------

.. tab-set-code::

  .. code-block:: java

    Optional<Alliance> ally = DriverStation.getAlliance();
    if (ally.isPresent()) {
        if (ally.get() == Alliance.Red) {
            <RED ACTION>
        }
        if (ally.get() == Alliance.Blue) {
            <BLUE ACTION>
        }
    }
    else {
        <NO COLOR YET ACTION>
    }

  .. code-block:: c++

    using frc::DriverStation::Alliance;
    if (auto ally = frc::DriverStation::GetAlliance()) {
        if (ally.value() == Alliance::kRed) {
            <RED ACTION>
        }
        if (ally.value() == Alliance::kBlue) {
            <BLUE ACTION>
        }
    }
    else {
        <NO COLOR YET ACTION>
    }

  .. code-block:: Python

    from wpilib import DriverStation

    ally = DriverStation.getAlliance()
    if ally is not None:
        if ally == DriverStation.Alliance.kRed:
            <RED ACTION>
        elif ally == DriverStation.Alliance.kBlue:
            <BLUE ACTION>
    else:
        <NO COLOR YET ACTION>
