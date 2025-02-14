# Miniproject 1

I used the [OSM Web Wizard](https://sumo.dlr.de/docs/Tutorials/OSMWebWizard.html) to extract the primary and secondary roadways around GMU to look at traffic flowing through the intersection of 123 and Braddock on Braddock Rd.

This is a helpful tutorial: [Driving in Cirlces](https://github.com/eclipse-sumo/sumo/blob/main/docs/web/docs/Tutorials/Driving_in_Circles.md).

## Open/Edit Network

To open the existing configuration open the `Braddock_GMU.netecfg` file using the `netedit` tool. This has information about which related files to load including scenery and routes.

### Route

Navigate to Demand > Route Mode, then you can click the roads (edges) on which to the route should run.

The routes are saved to the `Braddock_GMU.rou.xml` file.

### Flow

Navigate to Demand > Vehicle mode, then update the vehicle type (dropdown) to be `flow (over route)`.

You can easily edit the flow configuration by updating the text in the `Braddock_GMU.rou.xml` file.

### Editing a Signal

Navigate to Network > Traffic light mode. The light can be synced (extra credit) using the "join" mode available in that tab. The traffic light `type` is how you can update to use `static` vs `actuated` signaling.

Somehow you can configure the `phases` to update the signal phase time.

### Configuring Output

Output data must be requested from SUMO and the configuration is currently in `Braddock_GMU_output.xml`. Please see [Output Reference](https://sumo.dlr.de/docs/Simulation/Output/Lane-_or_Edge-based_Traffic_Measures.html) for more.

## Open/Run Simulation

To open the existing configuration open the `Braddock_GMU.sumocfg` using the Sumo GUI. This file contains pointers to the files to run the simulation, so it will automatically pick up any edits saved to the file on subsequent reopens.
