---
title: 通話データ コネクタの構成
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Online ツールを使用して Skype for Business オンプレミスからのテレメトリを表示できる通話データ コネクタを構成する手順。
ms.openlocfilehash: f78d59d02964bd826fc705bc193cae3e21b293a5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118996"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="70ad4-103">通話データ コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="70ad4-103">Configure Call Data Connector</span></span>

<span data-ttu-id="70ad4-104">この記事では、Skype for Business Online 通話品質ダッシュボード (CQD) ツールと通話分析 (CA) ツールを使用して Skype for Business Server 通話品質データを表示できる単一のツールセットである通話データ コネクタを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="70ad4-105">役割要件やハイブリッド接続のセットアップなど、通話データ コネクタの利点と前提条件の詳細については [、「Plan Call Data Connector」を参照してください](plan-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="70ad4-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="70ad4-106">監視を有効にする</span><span class="sxs-lookup"><span data-stu-id="70ad4-106">Enable Monitoring</span></span>
 
<span data-ttu-id="70ad4-107">ローカルの LCSCdr データベースと QoEMetrics データベースを使用して、フロントエンド プールの監視で通話データ記録 (CDR) および QoE (QoE) データ収集を構成する必要があります。それ以外の場合、Call Analytics と Call Quality ダッシュボードは、データを取得して機能しません。</span><span class="sxs-lookup"><span data-stu-id="70ad4-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="70ad4-108">通話データ コネクタを構成する前に [、「Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) での監視の展開」の手順に従って、CDR と QoE の両方と基本的な監視を構成します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70ad4-109">フロントエンド プールで監視が有効になっていない場合、データ コネクタの呼び出しは機能しません。</span><span class="sxs-lookup"><span data-stu-id="70ad4-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="70ad4-110">通話データ コネクタを有効にする</span><span class="sxs-lookup"><span data-stu-id="70ad4-110">Enable Call Data Connector</span></span>

<span data-ttu-id="70ad4-111">データ コネクタの呼び出しを構成および有効にするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="70ad4-112">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="70ad4-112">Cmdlet</span></span>| <span data-ttu-id="70ad4-113">説明</span><span class="sxs-lookup"><span data-stu-id="70ad4-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="70ad4-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="70ad4-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="70ad4-115">オンライン データ コレクターを確立するオンライン コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="70ad4-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="70ad4-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="70ad4-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="70ad4-117">既存のオンライン データ コレクターを取得するオンライン コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="70ad4-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="70ad4-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="70ad4-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="70ad4-119">このコマンドレットによって作成された接続情報を取得するオンプレミスのコマンドレットNew-CsCloudCallDataConnectionします。</span><span class="sxs-lookup"><span data-stu-id="70ad4-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="70ad4-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="70ad4-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="70ad4-121">オンプレミスのコマンドレットで、New-CsCloudCallDataConnection コマンドレットによって作成された接続情報のオンプレミス コピーを保存します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="70ad4-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="70ad4-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="70ad4-123">コネクタを有効または無効にし、スコープ レベルをカスタマイズできるオンプレミスのコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="70ad4-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="70ad4-124">構成を消去して最初から実行するには、Remove-csclouddatconnectorconfiguration コマンドレットを使用してください。</span><span class="sxs-lookup"><span data-stu-id="70ad4-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="70ad4-125">環境を構成する</span><span class="sxs-lookup"><span data-stu-id="70ad4-125">Configure your environment</span></span> 

<span data-ttu-id="70ad4-126">オンライン データ コレクターを有効にするために環境を構成するには、まず管理者として Skype for Business Online PowerShell にログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70ad4-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="70ad4-127">詳細については [、「Manage Skype for Business Online with Office 365 PowerShell」を参照してください](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="70ad4-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="70ad4-128">Skype for Business Online PowerShell にログインするには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="70ad4-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="70ad4-129">Skype for Business Server 2019 管理シェルから (推奨される方法)</span><span class="sxs-lookup"><span data-stu-id="70ad4-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="70ad4-130">別の PowerShell セッションから</span><span class="sxs-lookup"><span data-stu-id="70ad4-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="70ad4-131">Skype for Business Server 管理シェルから Skype for Business Online PowerShell にログインする (推奨される方法)</span><span class="sxs-lookup"><span data-stu-id="70ad4-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="70ad4-132">コネクタを初めて有効にする場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="70ad4-133">接続が既に存在するというエラーが発生した場合は、テナントの通話データ接続が既に存在することを意味します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="70ad4-134">この場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="70ad4-135">別の PowerShell セッションから Skype for Business Online PowerShell にログインする (オプションの方法)</span><span class="sxs-lookup"><span data-stu-id="70ad4-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="70ad4-136">コネクタを初めて有効にする場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="70ad4-137">接続が既に存在するというエラーが発生した場合は、テナントの通話データ接続が既に存在することを意味します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="70ad4-138">この場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="70ad4-139">上記のコマンドの出力にはトークン値が含まれています。この値は、次のようにオンプレミス環境を構成するときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="70ad4-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="70ad4-140">Skype for Business Server 管理シェル内で、次のコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="70ad4-141">スコープを構成する</span><span class="sxs-lookup"><span data-stu-id="70ad4-141">Configure the scope</span></span>

<span data-ttu-id="70ad4-142">Skype for Business Server 管理シェル内の Set-CsCloudCallDataConnectorConfiguration コマンドレットを使用して、特定のサイトまたは Skype for Business Server 展開全体に対して通話データ コネクタを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="70ad4-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="70ad4-143">たとえば、次のコマンドを使用すると、グローバル スコープでデータ コネクタの呼び出しが有効になります。</span><span class="sxs-lookup"><span data-stu-id="70ad4-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="70ad4-144">グローバル設定に加えて、Call Data Connector 構成設定をサイト スコープに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="70ad4-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="70ad4-145">これにより、監視に関して管理の柔軟性が向上します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="70ad4-146">たとえば、次の例に示すように、管理者は Redmond サイトの通話データ コネクタ転送を有効にできますが、ダブリン サイトの通話データ コネクタ転送を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="70ad4-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="70ad4-147">サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="70ad4-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="70ad4-148">たとえば、グローバル スコープでデータ コネクタ転送の呼び出しが有効になっているが、サイト スコープ (Redmond サイトの場合) では無効になっているとします。</span><span class="sxs-lookup"><span data-stu-id="70ad4-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="70ad4-149">つまり、通話の詳細記録と QoE 情報は、Redmond サイトのユーザーに転送されません。</span><span class="sxs-lookup"><span data-stu-id="70ad4-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="70ad4-150">ただし、他のサイトのユーザー (つまり、Redmond サイト設定の代わりにグローバル設定によって管理されるユーザー) は、通話の詳細記録と QoE 情報を転送します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="70ad4-151">通話データ コネクタで使用される最もよく使用される設定の値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="70ad4-152">プロパティ</span><span class="sxs-lookup"><span data-stu-id="70ad4-152">Property</span></span>|<span data-ttu-id="70ad4-153">説明</span><span class="sxs-lookup"><span data-stu-id="70ad4-153">Description</span></span>|<span data-ttu-id="70ad4-154">既定値</span><span class="sxs-lookup"><span data-stu-id="70ad4-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="70ad4-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="70ad4-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="70ad4-156">データ コネクタの呼び出しが有効かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="70ad4-157">True の場合、監視レコードはオンライン監視に転送されます。</span><span class="sxs-lookup"><span data-stu-id="70ad4-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="70ad4-158">$False</span><span class="sxs-lookup"><span data-stu-id="70ad4-158">$False</span></span>  <br/> |
| <span data-ttu-id="70ad4-159">ID</span><span class="sxs-lookup"><span data-stu-id="70ad4-159">Identity</span></span> | <span data-ttu-id="70ad4-160">コマンドのスコープ レベル (グローバルまたはサイト) を決定します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="70ad4-161">global</span><span class="sxs-lookup"><span data-stu-id="70ad4-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="70ad4-162">通話データ コネクタを無効にする</span><span class="sxs-lookup"><span data-stu-id="70ad4-162">Disable Call Data Connector</span></span>

<span data-ttu-id="70ad4-163">通話データ コネクタを無効にしても、監視ストアとフロントエンド プールとの関連付けは解除されません。また、バックエンド監視データベースをアンインストールしたり、その他の影響を与える場合もありません。</span><span class="sxs-lookup"><span data-stu-id="70ad4-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="70ad4-164">通話データ コネクタを無効にすると、Skype for Business Server が通話データをクラウドにアップロードするのを停止します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="70ad4-165">Skype for Business Server 管理シェル内の Set-CsCloudCallDataConnectorConfigurationコマンドレットを使用して、データ コネクタの呼び出しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="70ad4-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="70ad4-166">たとえば、次のコマンドは、EnableCallDataConnector プロパティを次の値に設定して、グローバル スコープでデータ コネクタの呼び出しを$False。</span><span class="sxs-lookup"><span data-stu-id="70ad4-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="70ad4-167">クラウドへの通話データのアップロードを再開する場合は、次の例に示すように、EnableCallDataConnector プロパティを $True に戻します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="70ad4-168">オンライン ダッシュボードを使用してオンプレミス のデータを表示する</span><span class="sxs-lookup"><span data-stu-id="70ad4-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="70ad4-169">通話データ コネクタを有効にすると、「通話分析を使用して品質の低下をトラブルシューティングし[、Microsoft Teams](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)および Skype for [](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) Business Online の通話品質ダッシュボードを有効にし、使用する」の説明に従って、通話分析ダッシュボードまたは通話品質ダッシュボードでオンプレミス通話データを表示できます。</span><span class="sxs-lookup"><span data-stu-id="70ad4-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="70ad4-170">詳細情報</span><span class="sxs-lookup"><span data-stu-id="70ad4-170">For more information</span></span>

<span data-ttu-id="70ad4-171">コマンドレットの詳細については、Skype for Business Server 管理シェルGet-Helpコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="70ad4-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="70ad4-172">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="70ad4-172">For example:</span></span>

<span data-ttu-id="70ad4-173">Get-Help Get-CsCloudCallDataConnector |もっとその</span><span class="sxs-lookup"><span data-stu-id="70ad4-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="70ad4-174">Get-Help Set-CsCloudCallDataConnector |もっとその</span><span class="sxs-lookup"><span data-stu-id="70ad4-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="70ad4-175">Get-Help Set-CsCloudCallDataConnectorConfiguration |もっとその</span><span class="sxs-lookup"><span data-stu-id="70ad4-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>