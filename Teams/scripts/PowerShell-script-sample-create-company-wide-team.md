---
title: "PowerShell スクリプトの例 - Microsoft Teams で会社全体のチームを作成する"
author: ninadara
ms.author: ninadara
manager: lolaj
ms.date: 02/07/2018
ms.topic: article
ms.service: msteams
description: "この PowerShell スクリプトを使用して、会社全体にわたるパブリックなチームを Teams で作成します。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: a22eddd2051526753df86d32e833feb89ce0625f
ms.sourcegitcommit: 46ca433590a4c3aefbe2fb777542bb0b332563bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2018
---
<a name="powershell-script-sample---create-a-company-wide-team-in-microsoft-teams"></a>PowerShell スクリプトの例 - Microsoft Teams で会社全体のチームを作成する
-------------------------------------------------------------------------

この PowerShell スクリプトにより、会社全体にわたるパブリックなチームが Teams で作成されます。 このスクリプトでは会社全体にわたるパブリックなチームを作成するために、MicrosoftTeams PowerShell モジュール (現在ベータ版) を使用します。 また、テナント内のユーザーのリストを取り込むために、AzureAD PowerShell モジュールも使用します。 

この PowerShell スクリプトの使用方法の詳細については、「[PowerShell を使用して Teams で会社全体のチームを作成する](../Company-wide-team-creation-powershell.yml)」を確認してください。

PowerShell をこれまでに使用したことがなく、使用開始のためのヘルプが必要な場合は、「[Azure PowerShell の概要](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)」をご覧ください。


## <a name="sample-script"></a>サンプル スクリプト

> [!TIP]
> PowerShell スクリプト ファイルは拡張子が .PS1 のテキスト ファイルです。 このスクリプトを使用するには、[**コピー**] をクリックしてコードをテキスト ファイルに貼り付けます。 そのファイルを CreateCompanyWideTeam.ps1 というファイル名で保存します。これで、PowerShell スクリプトを取得したことになります。

````powershell
<#
.SYNOPSIS
This script allows you to create a company-wide team.
.DESCRIPTION
Use this script with the MicrosoftTeams PowerShell version 0.9.0 beta module to create a team with members and channels that you specify. Also leverages the AzureAD module to find all members to add.
.PARAMETER Owners
The comma-separated list of owners for your Team, who handle team settings and membership management. The owners should be specified by their User Principal Name. You must specify a minimum of two owners.
.PARAMETER TeamName
The name of your company-wide team. For example, this could be your company name.
.PARAMETER TeamDescription
The description of your company-wide team, in quotes.
.PARAMETER Channels
The comma-separated list of names of all the initial channels you want to set up. For example: "Announcements","Social at Work","Teamwork at Contoso".
.PARAMETER GroupID
If you have already created the group for your company-wide team, specify its GroupID. You can get this value from the display of the “Get-AzureADGroup | Sort DisplayName | Select DisplayName,ObjectID” command. This script had an issue during the rest of the execution and stopped early. 
.PARAMETER Members
The comma-separated list of members for your team that you want to manually add. To use this script a minimum of two members must be added. The members should be specified by their User Principal Name. To manually just add a single member, use the “Add-TeamUser -GroupId $IdOfGroup -Role Member -User $member” command.
#>
param(
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Owners,
    [Parameter(Mandatory=$false)][System.String]$TeamName,
    [Parameter(Mandatory=$false)][System.String]$TeamDescription,
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Channels,
    [Parameter(Mandatory=$false)][System.String]$GroupID,
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Members
)

function Create-Team(){
    Write-Host("Starting Team Creation")
    $GroupID = (New-Team -DisplayName $TeamName -AccessType Public -Description $TeamDescription).GroupId

    if([string]::IsNullOrEmpty($GroupID)){
        Write-Host("Team creation failed, please investigate and try again")
        Return
    }

    Write-Host("Team GroupID:", $GroupID)

    return ,$GroupID
} 

 
function Add-Channels($IdOfGroup){
        Write-Host("Starting Channel addition")
    foreach($channel in $Channels)
        {
            Write-Host("Enter Channel Description for " + $channel + " channel")
            $channelDescription = Read-Host
            New-TeamChannel -GroupId $IdOfGroup -DisplayName $channel -Description $channelDescription
        }
}
 
 
function Add-Members ($IdOfGroup){
    Write-Host("Starting Member addition")
    $allUsersInTenant = $Members 

    ## Only fetch full user list, if one isn't supplied
    if([string]::IsNullOrEmpty($Members))
    {
        $Error.Clear()
 

        Write-Host("Starting connection to AzureAD module") 
        Connect-AzureAD
 
        if($Error){
            Write-Host("Unable to connect to AzureAD. Please investigate and try again. To install the commandlet, use this command: Install-Module AzureAD")
            Return
        }
    
        

       ## Fetch all the users and create the member list
        $allUsersInTenant = (Get-AzureADUser).UserPrincipalName 

 
        Disconnect-AzureAD
    } 
    
    $NotAddedMembers = [System.Collections.ArrayList]@()
    $existingTeamMembers = (Get-TeamUser -GroupId $IdOfGroup).User

    foreach($user in $allUsersInTenant){
        $Error.Clear()

        if(!$existingTeamMembers.Contains($user)){
            Write-Host($user)

            if($Owners.Contains($user)){
                Add-TeamUser -GroupId $IdOfGroup -Role Owner -User $user.ToString()
                
                if($Error){
                    $NotAddedMembers.Add([Tuple]::Create($user,"Owner"))
                }
            }
            else{
                Add-TeamUser -GroupId $IdOfGroup -Role Member -User $user.ToString()
                
                if($Error) {
                    $NotAddedMembers.Add([Tuple]::Create($user,"Member"))
                }
            }
        }
    } 

    if($NotAddedMembers.Count > 0) {
        Write-Host("There are some members that did not get added, please retry these specific users")
        Write-Host($NotAddedMembers)
    } 


    ##Clear member addition errors
    $Error.Clear()
}
 
 
 
 
##Main Script
$Error.Clear()
Write-Host("Starting connection to MicrosoftTeams module") 

Connect-MicrosoftTeams
 
if($Error){
    Write-Host("There was an error installing\connecting to the Microsoft Teams PowerShell module. Please investigate. To install the module use the follow command: Install-Module MicrosoftTeams ")
    Return
}

##Create the team if existing GroupID isn't supplied. It's possible a Tenant Wide team was created, but there was an error adding members.
if([string]::IsNullOrEmpty($GroupID)){

    if([string]::IsNullOrEmpty($TeamName)){
        Write-Host("Missing an argument for parameter 'TeamName' and 'GroupID'. Specify a parameter of type 'System.String' and try again for either GroupID or TeamName and TeamDescription")
        Return
    }
    $GroupID = Create-Team
} 
 
if($Channels.Count -gt 0){
    Add-Channels $GroupID
} 

Add-Members $GroupID 
 
Disconnect-MicrosoftTeams

````


## <a name="script-explanation"></a>スクリプトの説明


この PowerShell スクリプトの使用方法の詳細については、「[PowerShell を使用して Teams で会社全体のチームを作成する](../Company-wide-team-creation-powershell.yml)」を確認してください。

このスクリプトには次の 5 つのセクションがあります (上から下に順番に示しています)。
1. **ドキュメンテーションと変数の定義**
2. **関数 Create-Team**: 必要に応じてチームを作成します。 GroupID を指定しない場合、このセクションは指定された TeamName と TeamDescription を使用してチームを作成します。
3. **関数 Add-Channels**: チャネルを指定した場合、ここでチャネルの説明が要求されて、チャネルが作成されます。 
4. **関数 Add-Members**: メンバー管理のすべてを行います。 このセクションは AzureAD に接続して、ユーザーのセットを取り込み、メンバー リストが提供されていない場合にそれらのユーザーをチームに追加します。 既にチームに所属しているメンバーの追加ではなく、所有者とメンバーを追加するロジックを処理します。 
5. **メイン プログラム**: これは関数が実行されるようにする命令です。 


