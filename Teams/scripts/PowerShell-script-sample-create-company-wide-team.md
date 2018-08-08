---
title: PowerShell スクリプトの例 - Microsoft Teams で会社全体のチームを作成する
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 02/07/2018
ms.topic: article
ms.service: msteams
description: この PowerShell スクリプトを使用して、会社全体にわたるパブリックなチームを Teams で作成します。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 26933c97aaa5d16c28a771e3d45c31174b807c07
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "18999160"
---
<a name="powershell-script-sample---create-a-company-wide-team-in-microsoft-teams"></a><span data-ttu-id="c565e-103">PowerShell スクリプトの例 - Microsoft Teams で会社全体のチームを作成する</span><span class="sxs-lookup"><span data-stu-id="c565e-103">PowerShell Script Sample - Create a company-wide team in Microsoft Teams</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="c565e-104">この PowerShell スクリプトにより、会社全体にわたるパブリックなチームが Teams で作成されます。</span><span class="sxs-lookup"><span data-stu-id="c565e-104">This PowerShell script creates a public, company-wide team in Teams.</span></span> <span data-ttu-id="c565e-105">このスクリプトでは会社全体にわたるパブリックなチームを作成するために、MicrosoftTeams PowerShell モジュール (現在ベータ版) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c565e-105">The script uses the MicrosoftTeams PowerShell module (currently in beta) to create a public, company-wide team.</span></span> <span data-ttu-id="c565e-106">また、テナント内のユーザーのリストを取り込むために、AzureAD PowerShell モジュールも使用します。</span><span class="sxs-lookup"><span data-stu-id="c565e-106">It also uses the AzureAD PowerShell module to fetch the list of users in your tenant.</span></span> 

<span data-ttu-id="c565e-107">この PowerShell スクリプトの使用方法の詳細については、「[PowerShell を使用して Teams で会社全体のチームを作成する](../Company-wide-team-creation-powershell.yml)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c565e-107">For complete instructions on using this PowerShell script, check out our tutorial, [Create a company-wide team in Teams using PowerShell](../Company-wide-team-creation-powershell.yml).</span></span>

<span data-ttu-id="c565e-108">PowerShell をこれまでに使用したことがなく、使用開始のためのヘルプが必要な場合は、「[Azure PowerShell の概要](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c565e-108">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="sample-script"></a><span data-ttu-id="c565e-109">サンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="c565e-109">Sample script</span></span>

> [!TIP]
> <span data-ttu-id="c565e-110">PowerShell スクリプト ファイルは拡張子が .PS1 のテキスト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="c565e-110">A PowerShell script file is a text file with a .PS1 extension.</span></span> <span data-ttu-id="c565e-111">このスクリプトを使用するには、[**コピー**] をクリックしてコードをテキスト ファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c565e-111">To use this script, click **Copy** and then paste the code into a text file.</span></span> <span data-ttu-id="c565e-112">そのファイルを CreateCompanyWideTeam.ps1 というファイル名で保存します。これで、PowerShell スクリプトを取得したことになります。</span><span class="sxs-lookup"><span data-stu-id="c565e-112">Save it with the filename CreateCompanyWideTeam.ps1, and you've got a PowerShell script.</span></span>

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


## <a name="script-explanation"></a><span data-ttu-id="c565e-113">スクリプトの説明</span><span class="sxs-lookup"><span data-stu-id="c565e-113">Script explanation</span></span>


<span data-ttu-id="c565e-114">この PowerShell スクリプトの使用方法の詳細については、「[PowerShell を使用して Teams で会社全体のチームを作成する](../Company-wide-team-creation-powershell.yml)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c565e-114">For complete instructions on using this PowerShell script, check out our tutorial, [Create a company-wide team in Teams using PowerShell](../Company-wide-team-creation-powershell.yml)</span></span>

<span data-ttu-id="c565e-115">このスクリプトには次の 5 つのセクションがあります (上から下に順番に示しています)。</span><span class="sxs-lookup"><span data-stu-id="c565e-115">There are 5 sections to this script (listed in order from top to bottom):</span></span>
1. <span data-ttu-id="c565e-116">**ドキュメンテーションと変数の定義**</span><span class="sxs-lookup"><span data-stu-id="c565e-116">**Documentation and variable definitions**</span></span>
2. <span data-ttu-id="c565e-117">**関数 Create-Team**: 必要に応じてチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="c565e-117">**Function Create-Team**: Creates a team if necessary.</span></span> <span data-ttu-id="c565e-118">GroupID を指定しない場合、このセクションは指定された TeamName と TeamDescription を使用してチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="c565e-118">If you don't specify a GroupID, this section will create the team with the specified TeamName and TeamDescription.</span></span>
3. <span data-ttu-id="c565e-119">**関数 Add-Channels**: チャネルを指定した場合、ここでチャネルの説明が要求されて、チャネルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c565e-119">**Function Add-Channels**: If you've specified channels, this is where the channel description gets requested, and then the channel gets created.</span></span> 
4. <span data-ttu-id="c565e-120">**関数 Add-Members**: メンバー管理のすべてを行います。</span><span class="sxs-lookup"><span data-stu-id="c565e-120">**Function Add-Members**: This does all member management.</span></span> <span data-ttu-id="c565e-121">このセクションは AzureAD に接続して、ユーザーのセットを取り込み、メンバー リストが提供されていない場合にそれらのユーザーをチームに追加します。</span><span class="sxs-lookup"><span data-stu-id="c565e-121">This section connects to AzureAD,  fetches a set of users, and adds them to the team if you don’t provide a member list.</span></span> <span data-ttu-id="c565e-122">既にチームに所属しているメンバーの追加ではなく、所有者とメンバーを追加するロジックを処理します。</span><span class="sxs-lookup"><span data-stu-id="c565e-122">It handles the logic of adding owners and members, and not adding members who already belong to the team.</span></span> 
5. <span data-ttu-id="c565e-123">**メイン プログラム**: これは関数が実行されるようにする命令です。</span><span class="sxs-lookup"><span data-stu-id="c565e-123">**Main program**: This is the order in which the functions get executed.</span></span> 


