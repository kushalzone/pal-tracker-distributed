# pal-tracker-distributed
PIVOTAL Platform  Acceleration Lab - Sessions. 

*Commonly used commands*

<pre>
====CLOUD FOUNDRY====
cf login -a api.run.pivotal.io
cf push
cf push -f manifest-registration.yml
cf marketplace
cf services
cf target -s review
cf create-service ${MYSQL_SERVICE_NAME} ${PLAN_NAME} tracker-database
cf target -s production
cf create-service ${MYSQL_SERVICE_NAME} ${PLAN_NAME} tracker-database
cf create-service p-service-registry standard tracker-service-registry
cf target -s review
cf bind-service pal-tracker tracker-database
cf target -s production
cf bind-service pal-tracker tracker-database
cf create-space review
cf create-space production
cf restart moviefun
cf bind-service moviefun movies-mysql
cf restage moviefun
cf apps
cf logout

====FLYWAY COMMANDS====
flyway -url="jdbc:mysql://localhost:3306/tracker_dev" -locations=filesystem:databases/tracker clean migrate
flyway -url="jdbc:mysql://localhost:3306/tracker_test" -locations=filesystem:databases/tracker clean migrate


===LINUX COMMANDS==
apt search PACKAGE
sudo apt install git
brew install cloudfoundry/tap/cf-cli
!4 (Runs the 4th command from history)


====GRADLE COMMANDS====
./gradlew build
mkdir -p  ~/workspace/use-gradle
cd ~/workspace/use-gradle
gradle wrapper
./gradlew tasks
touch build.gradle
./gradlew sayHello sayGoodbye
./gradlew sH sG
./gradlew clean build --dry-run
./gradlew clean build

====Concourse FLY Commands====
fly --target pal-concourse login --concourse-url ${CONCOURSE_URL} --team-name ${TEAM_NAME}
fly -t pal-concourse set-pipeline -p pal-tracker --load-vars-from ci/variables.yml -c ci/pipeline.yml
fly -t pal-concourse destroy-pipeline -p pal-tracker
fly -t pal-concourse unpause-pipeline -p pal-tracker
fly set-pipeline
fly validate-pipeline
fly format-pipeline
fly pipelines
fly rename-pipeline
fly pause-pipeline
fly unpause-pipeline
fly expose-pipeline
fly hide-pipeline
fly get-pipeline
fly destroy-pipeline

====GIT COMMANDS=====
git remote add origin2 https://github.com/{useridhere}/pal-tracker-distributed.git
git push origin2 --force

</pre>

Weblinks:
<br/>Concourse: https://concourse-ci.org/
<br/>FlywayDB: https://flywaydb.org/
<br/>App Continnum: http://www.appcontinuum.io/

