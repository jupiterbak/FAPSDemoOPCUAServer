# DEMO OPC UA Servers - "OPC UA Knowledge Completion via Graph Embedding and Reinforcement Learning"

This is repository of the DEMO OPC UA-servers used to validate the results of the paper entitled "OPC UA Knowledge Completion via Graph Embedding and Reinforcement Learning". The servers import multiple nodesets copied from the official releases of the OPC Foundation: [https://github.com/OPCFoundation/UA-Nodeset](https://github.com/OPCFoundation/UA-Nodeset)

The default port of the servers application are ***4840*** and can be changed in the configuration file ***config_dataset_one.yml*** and ***config_dataset_two.yml***.

## Requirements

* NodeJs : The Backend requires NodeJs and a node global package npm.
* Git
* Dockers: For a container installation, Docker is required. Please refer to the docker documentation for docker installation.

## Installation

### NodeJS

Step 1: Clone this repo.

Step 2: Install the dependencies.

```bash
npm install
```

Step 2: Start the application. Run the following

```bash
npm start
```

After a sucessfull startup the following output should be printed. Please notice the information that all modules have been sucessfully initialized and started.

```console

C:\GitHub\OPEN-ACCESS>npm start

2020-05-18 09:06:18 - [info] | [Dummy Server] : Server is now listening ... ( press CTRL+C to stop)
2020-05-18 09:06:18 - [info] | [Dummy Server] : port 4840
2020-05-18 09:06:18 - [info] | [Dummy Server] : The primary server endpoint url is opc.tcp://LAPLACE.FAPS.UNI-ERLANGEN.DE:4840

```
The OPCUA server is now accessible at [opc.tcp://LAPLACE.FAPS.UNI-ERLANGEN.DE:4840](opc.tcp://LAPLACE.FAPS.UNI-ERLANGEN.DE:4840).

### Deploy as a Microservice using Docker[Swarm]

You can also deploy as a microservice inside a Docker container:

Step 1: Clone the repo

Step 2: Build the Docker image

```bash
docker build -t opcua_server_skill_add .
```

Step 3: Run the Docker container locally:

```bash
docker run -p 4843:4843 -d opcua_server_skill_add
```

<!-- USAGE -->
## Usage

In order to configurethe server, the file ***config.yml*** has to be configured appropriately. For example the following configuration set the default port of the OPCUA server to 4843.


```yaml
default:
  server:
    port: 4843
    buildInfo:
      productName: "DummySkillServer - Add"
      buildNumber: "0001"
    ip: "0.0.0.0"
    endpointName: 'OPCUA@Siemens'
    username: 'root'
    password: 'root'
    allowAnonymous: false,
    serverInfo:
      applicationUri: "http://siemens.com/SkillOPCUA"
      productUri: "siemens.com/SP347_Example"
      applicationName: "SP347SkillEngineering@Siemens" 
    serverNodeSet: ["AutomationSkillType_OptionalStateMachine.xml","SkillADD_OptionalStateMachine.xml"]

```

<!-- CONTRIBUTING -->
## Contributing

Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<!-- LICENSE -->
## License

See `LICENSE` for more information.

<!-- CONTACT -->
## Contact

Jupiter Bakakeu - [@JBakakeu](https://twitter.com/JBakakeu) - jupiter.bakakeu@gmail.com