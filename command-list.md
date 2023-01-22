# Command List

./build.sh RunDatabaseMigrations
./build.sh UnitTests
./build.sh Restore
./build.sh CreateDatabase
./build.sh PrepareInputFiles
./build.sh Clean
./build.sh CompileDbUpMigrator
./build.sh PrepareSqlServer
./build.sh BuildAdministrationModuleIntegrationTests
./build.sh BuildAndUnitTests
./build.sh CompileDbUpMigratorForIntegrationTests
./build.sh BuildUserAccessModuleIntegrationTests
./build.sh BuildSystemIntegrationTests
./build.sh BuildPaymentsModuleIntegrationTests
./build.sh BuildMeetingsModuleIntegrationTests
./build.sh ArchitectureTests
./build.sh BuildAndUnitTests
./build.sh MigrateDatabase

=== Failed ===
./build.sh RunAllIntegrationTests
./build.sh RunSystemIntegrationTests
./build.sh RunPaymentsModuleIntegrationTests
./build.sh RunAdministrationModuleIntegrationTests
./build.sh RunMeetingsModuleIntegrationTests
./build.sh RunUserAccessModuleIntegrationTests


=== SUT How to Run ===
./build.sh PrepareSUT --DatabaseConnectionString "Server=127.0.0.1,1433;Database=MyMeetings;User=SA;Password=MyPass@word!;TrustServerCertificate=True;Encrypt=false" --SUTTestName CreateMeeting

