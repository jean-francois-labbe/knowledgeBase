#Manage boxes

## export vagrant managed box
vagrant package
-> package.box

##Add the package.box to vagrant box list

vagrant box add superbox package.box

## init a new box from a vagrant managed box
mkdir mybox
cd mybox
vagrant init superbox

#Import an ova from virtualbox
##The "metadata.json" file for the box 'interop_base' was not found.

You need to add a metatdata.json filte to the ova.

```bash
mkdir ova
mv <your_ova_file>.ova ova
cd ova
tar xvf <your_ova_file>.ova
mv <your_ova_file>.ova ../
echo "{"provider": "virtualbox"}" > metadata.json
tar xvf <your_ova_file>.ova
```
`vagrant add your_title <your_ova_file>.ova`
