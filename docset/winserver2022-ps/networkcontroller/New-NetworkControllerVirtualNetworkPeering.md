---
description: The New-NetworkControllerVirtualNetworkPeering cmdlet configures a peering between two virtual networks to enable connectivity between them.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 09/27/2021
online version: https://docs.microsoft.com/powershell/module/networkcontroller/new-networkcontrollervirtualnetworkpeering?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerVirtualNetworkPeering
---

# New-NetworkControllerVirtualNetworkPeering

## SYNOPSIS
Creates a peering between two virtual networks to enable connectivity between them.

## SYNTAX

```
New-NetworkControllerVirtualNetworkPeering [-VirtualNetworkId] <String> [-ResourceId] <String>
 [-Properties] <VirtualNetworkPeeringProperties> [[-ResourceMetadata] <ResourceMetadata>] [[-Etag] <String>]
 [-Force] -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 [-PassInnerException] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetworkControllerVirtualNetworkPeering** cmdlet creates a peering between two virtual networks to enable connectivity between them.

## EXAMPLES

### Example 1: Create a virtual network peering
```powershell
$peeringProperties = New-Object Microsoft.Windows.NetworkController.VirtualNetworkPeeringProperties
$peeringProperties.remoteVirtualNetwork = Get-NetworkControllerVirtualNetwork -ConnectionUri "https://woodgrove01" -ResourceId "Woodgrove_VNet1"
New-NetworkControllerVirtualNetworkPeering -VirtualNetworkId "Contoso_VNet1" -ResourceId "ContosotoWoodgrove" -Properties $peeringProperties -ConnectionUri "https://woodgrove01"
```

This example creates a virtual network peering between subnets that belong to two fictional companies, Contoso and Woodgrove.

The first command creates a properties object for the virtual network peering.

The second command adds the virtual network for the Woodgrove company.

The final command creates the peering for the Contoso company side.
It uses the properties object that specifies the Woodgrove side.

This example sets up only the peering for the Contoso side of the peering.
A similar set of commands needs to be run for the Woodgrove side.

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
Specify this parameter only if you run this cmdlet on a computer that is not part of the network controller cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionUri
Specifies the Uniform Resource Identifier (URI) of a Network Controller.
The cmdlet creates a virtual network peering for that controller.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user credential that has permission to perform this action.
The default value is the current user.

This user must be present in the security group provided in the **ClientSecurityGroup** parameter in the `Install-NetworkController` cmdlet.
Specify this parameter only if you run this cmdlet on a computer that is not part of the network controller cluster.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Etag
Specifies the entity tag (ETag) parameter of the resource.
An ETag is an HTTP response header returned by an HTTP-compliant web server used to determine change in the content of a resource at a given URL.
The value of the header is an opaque string representing the state of the resource at the time the response was generated.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassInnerException
This thumbprint must also be provided in the **ClientCertificateThumbprint** parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

The thumbprint must be provided only if the network controller client authentication is X509 certificates.
**Get-NetworkController** retrieves that client authentication and authorization information.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Properties
Specifies the properties of the virtual network peering.

```yaml
Type: VirtualNetworkPeeringProperties
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies the resource ID of the virtual network peering to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceMetadata
Specifies metadata information for the client, such as the tenant ID, group ID, and resource name.

```yaml
Type: ResourceMetadata
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkId
Specified the ID of a virtual network.
This cmdlet creates a peering for that network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Windows.NetworkController.VirtualNetworkPeeringProperties

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Get-NetworkControllerVirtualNetwork](Get-NetworkControllerVirtualNetwork.md)

[Get-NetworkControllerVirtualNetworkPeering](Get-NetworkControllerVirtualNetworkPeering.md)

[Remove-NetworkControllerVirtualNetworkPeering](Remove-NetworkControllerVirtualNetworkPeering.md)
