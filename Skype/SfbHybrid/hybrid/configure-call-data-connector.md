---
title: 通話データコネクタを構成する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 通話データコネクタを構成する手順を説明します。これにより、skype for Business オンプレミスのテレメトリを Skype for Business Online ツールを使用して表示できるようになります。
ms.openlocfilehash: 4d472ce49a3059df7286c647b013abe321b9fd15
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963045"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="daaec-103">通話データコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="daaec-103">Configure Call Data Connector</span></span>

<span data-ttu-id="daaec-104">この記事では、Skype for Business Online 通話品質ダッシュボード (CQD) およびコール分析 (CA) ツールを使用して Skype for business Server の通話品質データを表示できるようにする単一のツールセットを、通話データコネクタを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="daaec-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="daaec-105">コールデータコネクタの利点と前提条件 (ロール要件、ハイブリッド接続の設定など) の詳細については、「 [Plan Call Data connector](plan-call-data-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="daaec-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="daaec-106">監視を有効にする</span><span class="sxs-lookup"><span data-stu-id="daaec-106">Enable Monitoring</span></span>
 
<span data-ttu-id="daaec-107">ローカルの LCSCdr および QoEMetrics データベースを使用して、コールデータ記録 (CDR) と QoE (Quality of Experience) データ収集をフロントエンドプールの監視に構成する必要があります。それ以外の場合、通話分析と通話品質ダッシュボードは、使用するデータを取得しません。</span><span class="sxs-lookup"><span data-stu-id="daaec-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="daaec-108">通話データコネクタを構成する前に、「 [Deploy monitoring In Skype For Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) 」に記載されている手順に従って、CDR と qoe の両方および基本的な監視を構成します。</span><span class="sxs-lookup"><span data-stu-id="daaec-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="daaec-109">フロントエンドプールで監視が有効になっていない場合、Call Data Connector は機能しません。</span><span class="sxs-lookup"><span data-stu-id="daaec-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="daaec-110">通話データコネクタを有効にする</span><span class="sxs-lookup"><span data-stu-id="daaec-110">Enable Call Data Connector</span></span>

<span data-ttu-id="daaec-111">Call Data Connector を構成して有効にするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="daaec-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="daaec-112">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="daaec-112">Cmdlet</span></span>| <span data-ttu-id="daaec-113">説明</span><span class="sxs-lookup"><span data-stu-id="daaec-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="daaec-114">CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="daaec-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="daaec-115">オンラインデータコレクターを確立するオンラインコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="daaec-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="daaec-116">CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="daaec-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="daaec-117">既存のオンラインデータコレクターを取得するオンラインコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="daaec-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="daaec-118">CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="daaec-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="daaec-119">CsCloudCallDataConnection コマンドレットによって作成された接続情報を取得するオンプレミスのコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="daaec-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="daaec-120">CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="daaec-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="daaec-121">CsCloudCallDataConnection コマンドレットによって作成された接続情報のオンプレミスコピーを保存するオンプレミスのコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="daaec-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="daaec-122">CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="daaec-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="daaec-123">コネクタを有効または無効にして、スコープレベルをカスタマイズできるオンプレミスのコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="daaec-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="daaec-124">構成を消去して最初からやり直すには、「Remove-csclouddatコネクタ構成コマンドレット」を使用してください。</span><span class="sxs-lookup"><span data-stu-id="daaec-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="daaec-125">環境を構成する</span><span class="sxs-lookup"><span data-stu-id="daaec-125">Configure your environment</span></span> 

<span data-ttu-id="daaec-126">オンラインデータコレクターを有効にするように環境を構成するには、まず、管理者として Skype for Business Online PowerShell にログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="daaec-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="daaec-127">詳細については、「 [Office 365 PowerShell を使用して Skype For Business Online を管理](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="daaec-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="daaec-128">Skype for Business Online PowerShell にログインするには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="daaec-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="daaec-129">Skype for Business Server 2019 管理シェル (推奨される方法)</span><span class="sxs-lookup"><span data-stu-id="daaec-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="daaec-130">別の PowerShell セッションから</span><span class="sxs-lookup"><span data-stu-id="daaec-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="daaec-131">Skype for business Server 管理シェルからの Skype for Business Online PowerShell へのログイン (推奨方法)</span><span class="sxs-lookup"><span data-stu-id="daaec-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="daaec-132">コネクタを初めて有効にする場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="daaec-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="daaec-133">接続が既に存在することを示すエラーが表示された場合は、テナントの通話データ接続が既に存在することを意味します。</span><span class="sxs-lookup"><span data-stu-id="daaec-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="daaec-134">この場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="daaec-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="daaec-135">別の PowerShell セッションからの Skype for Business Online PowerShell へのログイン (オプションのメソッド)</span><span class="sxs-lookup"><span data-stu-id="daaec-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="daaec-136">コネクタを初めて有効にする場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="daaec-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="daaec-137">接続が既に存在することを示すエラーが表示された場合は、テナントの通話データ接続が既に存在することを意味します。</span><span class="sxs-lookup"><span data-stu-id="daaec-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="daaec-138">この場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="daaec-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="daaec-139">上記のコマンドの出力には、次のようにオンプレミス環境を構成するときに必要になるトークン値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="daaec-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="daaec-140">Skype for Business Server 管理シェルで、次のコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="daaec-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="daaec-141">スコープを構成する</span><span class="sxs-lookup"><span data-stu-id="daaec-141">Configure the scope</span></span>

<span data-ttu-id="daaec-142">Skype for Business Server 管理シェル内から CsCloudCallDataConnectorConfiguration コマンドレットを使用して、特定のサイトまたは Skype for Business Server の展開全体に対して、Call Data Connector を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="daaec-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="daaec-143">たとえば、次のコマンドを実行すると、グローバルスコープで呼び出しデータコネクタが有効になります。</span><span class="sxs-lookup"><span data-stu-id="daaec-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="daaec-144">グローバル設定に加えて、通話データコネクタの構成設定をサイトスコープに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="daaec-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="daaec-145">これにより、監視に関してさらに管理の柔軟性が得られます。</span><span class="sxs-lookup"><span data-stu-id="daaec-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="daaec-146">たとえば、管理者は、次の例に示されているように、Redmond サイトに対して通話データコネクタ転送を有効にして、ダブリンサイトの通話データコネクタ転送を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="daaec-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="daaec-147">サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="daaec-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="daaec-148">たとえば、通話データコネクタ転送がグローバルスコープで有効になっていても、サイトスコープ (Redmond サイトの場合) で無効になっているとします。</span><span class="sxs-lookup"><span data-stu-id="daaec-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="daaec-149">これは、Redmond サイトのユーザーに対して、通話詳細記録と QoE 情報が転送されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="daaec-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="daaec-150">ただし、他のサイトのユーザー (つまり、Redmond サイト設定ではなくグローバル設定で管理されているユーザー) には、通話詳細記録と QoE 情報が転送されます。</span><span class="sxs-lookup"><span data-stu-id="daaec-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="daaec-151">次の表に、Call Data Connector で使用される最も一般的に使用される設定の値を示します。</span><span class="sxs-lookup"><span data-stu-id="daaec-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="daaec-152">プロパティ</span><span class="sxs-lookup"><span data-stu-id="daaec-152">Property</span></span>|<span data-ttu-id="daaec-153">説明</span><span class="sxs-lookup"><span data-stu-id="daaec-153">Description</span></span>|<span data-ttu-id="daaec-154">既定値</span><span class="sxs-lookup"><span data-stu-id="daaec-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="daaec-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="daaec-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="daaec-156">通話データコネクタが有効かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="daaec-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="daaec-157">True の場合、監視レコードはオンライン監視に転送されます。</span><span class="sxs-lookup"><span data-stu-id="daaec-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="daaec-158">$False</span><span class="sxs-lookup"><span data-stu-id="daaec-158">$False</span></span>  <br/> |
| <span data-ttu-id="daaec-159">ID</span><span class="sxs-lookup"><span data-stu-id="daaec-159">Identity</span></span> | <span data-ttu-id="daaec-160">コマンドのスコープレベルを指定します (グローバルまたはサイト)。</span><span class="sxs-lookup"><span data-stu-id="daaec-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="daaec-161">全体</span><span class="sxs-lookup"><span data-stu-id="daaec-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="daaec-162">通話データコネクタを無効にする</span><span class="sxs-lookup"><span data-stu-id="daaec-162">Disable Call Data Connector</span></span>

<span data-ttu-id="daaec-163">通話データコネクタを無効にしても、監視ストアとフロントエンドプールの関連付けは解除されません。また、その他のバックエンド監視データベースに影響を与えることもありません。</span><span class="sxs-lookup"><span data-stu-id="daaec-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="daaec-164">通話データコネクタを無効にすると、Skype for Business Server が通話データをクラウドにアップロードするのを停止します。</span><span class="sxs-lookup"><span data-stu-id="daaec-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="daaec-165">通話データコネクタを無効にするには、Skype for Business Server 管理シェルで CsCloudCallDataConnectorConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="daaec-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="daaec-166">たとえば、次のコマンドを実行すると、EnableCallDataConnector プロパティを $False に設定することによって、グローバルスコープの通話データコネクタが無効になります。</span><span class="sxs-lookup"><span data-stu-id="daaec-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="daaec-167">呼び出しデータのクラウドへのアップロードを再開する場合は、次の例に示すように、EnableCallDataConnector プロパティを $True に戻します。</span><span class="sxs-lookup"><span data-stu-id="daaec-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="daaec-168">オンラインダッシュボードを使用してオンプレミスデータを表示する</span><span class="sxs-lookup"><span data-stu-id="daaec-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="daaec-169">Call Data Connector が有効になっている場合は、「通話分析を使用して、[品質低下をトラブルシューティング](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)し、 [Microsoft Teams および Skype for Business Online の通話品質ダッシュボードをオンおよび使用](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)する」で説明されているように、通話分析ダッシュボードまたは通話品質ダッシュボードでオンプレミスの通話データを表示できます。</span><span class="sxs-lookup"><span data-stu-id="daaec-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="daaec-170">関連情報</span><span class="sxs-lookup"><span data-stu-id="daaec-170">For more information</span></span>

<span data-ttu-id="daaec-171">コマンドレットの詳細については、「Skype for Business Server 管理シェル」の「Get-help」コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="daaec-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="daaec-172">例:</span><span class="sxs-lookup"><span data-stu-id="daaec-172">For example:</span></span>

<span data-ttu-id="daaec-173">Get-help get-help CsCloudCallDataConnector |もっとその</span><span class="sxs-lookup"><span data-stu-id="daaec-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="daaec-174">Get-help CsCloudCallDataConnector |もっとその</span><span class="sxs-lookup"><span data-stu-id="daaec-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="daaec-175">Get-help CsCloudCallDataConnectorConfiguration |もっとその</span><span class="sxs-lookup"><span data-stu-id="daaec-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
