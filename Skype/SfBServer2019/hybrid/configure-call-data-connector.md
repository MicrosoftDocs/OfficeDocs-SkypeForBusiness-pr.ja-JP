---
title: 呼び出しデータ コネクタを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 呼び出すデータ コネクタを遠隔測定 Skype からのビジネスの設置型のビジネスのオンライン ・ ツールの Skype を使用して表示するを構成する方法の詳細については。
ms.openlocfilehash: 959bb182da91029fd43ebc3ccb99fb5a69d820b2
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838824"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="6045b-103">呼び出しデータ コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="6045b-103">Configure Call Data Connector</span></span>

<span data-ttu-id="6045b-104">この資料では、呼び出しデータ コネクタ - ビジネス サーバー品質の呼び出しのデータがビジネス オンライン呼び出し品質ダッシュ ボード (救難) および呼び出す分析 (CA) のツールの Skype を使用して Skype の表示を有効にする 1 つのツールセットを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6045b-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span> 

> [!NOTE]
> <span data-ttu-id="6045b-105">パブリック プレビュー リリースでは、分析機能の呼び出しのダッシュ ボードのみがあります。</span><span class="sxs-lookup"><span data-stu-id="6045b-105">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="6045b-106">データの電話コネクタの利点と、ロールの要件など、ハイブリッド接続のセットアップの前提条件の詳細については、[呼び出しデータ コネクタの計画](plan-call-data-connector.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6045b-106">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="6045b-107">監視を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6045b-107">Enable Monitoring</span></span>
 
<span data-ttu-id="6045b-108">呼び出してデータの記録 (CDR) を構成する必要があり、プールの監視、ローカル LCSCdr および QoEMetrics データベースをフロント エンドのエクスペリエンスの品質 (QoE) データの収集それ以外の場合、呼び出しの分析と品質のダッシュ ボードを呼び出すで使用するデータを取得はありません。</span><span class="sxs-lookup"><span data-stu-id="6045b-108">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="6045b-109">前に呼び出しデータ コネクタの構成、手順両方 CDR および QoE と同様に基本的な監視を構成するのには[Skype ビジネス サーバーの展開の監視](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md)を提供します。</span><span class="sxs-lookup"><span data-stu-id="6045b-109">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6045b-110">フロント エンド プールの監視が有効になっていない場合は、呼び出しデータ コネクタは機能しません。</span><span class="sxs-lookup"><span data-stu-id="6045b-110">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="6045b-111">呼び出しデータ コネクタを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6045b-111">Enable Call Data Connector</span></span>

<span data-ttu-id="6045b-112">構成をデータ コネクタの呼び出しを有効にするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6045b-112">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="6045b-113">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="6045b-113">Cmdlet</span></span>| <span data-ttu-id="6045b-114">説明</span><span class="sxs-lookup"><span data-stu-id="6045b-114">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="6045b-115">新しい-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="6045b-115">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="6045b-116">オンラインでのデータ コレクターを作成し、オンラインのコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="6045b-116">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="6045b-117">Get CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="6045b-117">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="6045b-118">既存のオンラインでのデータ コレクターを取得する、オンラインのコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="6045b-118">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="6045b-119">Get CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="6045b-119">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="6045b-120">新規 CsCloudCallDataConnection コマンドレットによって作成された接続情報を取得する設置型のコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="6045b-120">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="6045b-121">セット CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="6045b-121">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="6045b-122">設置型のコピーを新規 CsCloudCallDataConnection コマンドレットによって作成された接続情報を保存する設置型のコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="6045b-122">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="6045b-123">セット CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="6045b-123">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="6045b-124">有効にして、コネクタを無効にするまたはスコープ レベルのカスタマイズを可能にする設置コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="6045b-124">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

### <a name="configure-your-environment"></a><span data-ttu-id="6045b-125">お客様の環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="6045b-125">Configure your environment</span></span> 

<span data-ttu-id="6045b-126">オンラインでのデータ コレクターを有効にするように環境を構成するにする必要があります最初 Skype にビジネス オンライン PowerShell の管理者としてログオンします。</span><span class="sxs-lookup"><span data-stu-id="6045b-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="6045b-127">詳細については、[ビジネス、オンラインで Office 365 の PowerShell の Skype の管理](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6045b-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="6045b-128">ビジネス オンラインの PowerShell の Skype にログインするための 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6045b-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="6045b-129">(推奨される方法)、ビジネス サーバー 2019 管理シェルの Skype から</span><span class="sxs-lookup"><span data-stu-id="6045b-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="6045b-130">別の PowerShell セッションから</span><span class="sxs-lookup"><span data-stu-id="6045b-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="6045b-131">ビジネス オンライン PowerShell の Business Server 管理シェルには (推奨される方法) Skype から Skype にサインインします。</span><span class="sxs-lookup"><span data-stu-id="6045b-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="6045b-132">最初にコネクタを有効にする場合、は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6045b-132">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="6045b-133">接続が既に存在するエラーが発生する場合は、テナントの呼び出しのデータ接続を既にが存在することを意味します。</span><span class="sxs-lookup"><span data-stu-id="6045b-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="6045b-134">この例では、コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6045b-134">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="6045b-135">ビジネス オンライン PowerShell の別の PowerShell セッション (省略可能なメソッド) から Skype にサインインします。</span><span class="sxs-lookup"><span data-stu-id="6045b-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="6045b-136">最初にコネクタを有効にする場合、は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6045b-136">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="6045b-137">接続が既に存在するエラーが発生する場合は、テナントの呼び出しのデータ接続を既にが存在することを意味します。</span><span class="sxs-lookup"><span data-stu-id="6045b-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="6045b-138">この例では、コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6045b-138">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="6045b-139">上記のコマンドの出力には、次のように、オンプレミスの環境を構成するときに必要なトークンの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6045b-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="6045b-140">Business Server 管理シェルには、Skype 内で次のコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="6045b-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="6045b-141">スコープを構成します。</span><span class="sxs-lookup"><span data-stu-id="6045b-141">Configure the scope</span></span>

<span data-ttu-id="6045b-142">有効にできますデータ コネクタを呼び出して、特定のサイト、または、全体の Skype ビジネス サーバー配置の Business Server 管理シェルには、Skype 内からセット CsCloudCallDataConnectorConfiguration コマンドレットを使用しています。</span><span class="sxs-lookup"><span data-stu-id="6045b-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="6045b-143">たとえば、次のコマンドは、グローバル スコープでのデータ コネクタの呼び出しを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6045b-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="6045b-144">グローバルの設定では、データの電話コネクタの構成設定はサイト スコープに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6045b-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="6045b-145">監視する際に、追加の管理の柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="6045b-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="6045b-146">たとえば、管理者は、レドモンド サイトのデータ コネクタの呼び出しの転送を有効にするが、ダブリンのサイトのデータ コネクタの呼び出しの転送を無効にする例を次に示すように。</span><span class="sxs-lookup"><span data-stu-id="6045b-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="6045b-147">サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="6045b-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="6045b-148">たとえば、データ コネクタの呼び出しの転送がグローバル スコープで有効になっているが、(レドモンド サイトの) サイトのスコープで無効にします。</span><span class="sxs-lookup"><span data-stu-id="6045b-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="6045b-149">その手段の詳細記録と QoE の情報を呼び出すは、レドモンド サイトのユーザーには転送されません。</span><span class="sxs-lookup"><span data-stu-id="6045b-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="6045b-150">ただし、他のサイト (レドモンド サイトの設定ではなくグローバル設定によって管理されているユーザー) のユーザーは、通話の詳細記録と QoE の情報が転送されるがあります。</span><span class="sxs-lookup"><span data-stu-id="6045b-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="6045b-151">データ コネクタの呼び出しで使用される最も一般的に使用される設定の値は、次の表のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6045b-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="6045b-152">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6045b-152">Property</span></span>|<span data-ttu-id="6045b-153">説明</span><span class="sxs-lookup"><span data-stu-id="6045b-153">Description</span></span>|<span data-ttu-id="6045b-154">既定値</span><span class="sxs-lookup"><span data-stu-id="6045b-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6045b-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="6045b-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="6045b-156">データの電話コネクタが有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6045b-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="6045b-157">True の場合、オンラインでの監視を監視レコードが転送されます。</span><span class="sxs-lookup"><span data-stu-id="6045b-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="6045b-158">$False</span><span class="sxs-lookup"><span data-stu-id="6045b-158">$False</span></span>  <br/> |
| <span data-ttu-id="6045b-159">ID </span><span class="sxs-lookup"><span data-stu-id="6045b-159">Identity</span></span> | <span data-ttu-id="6045b-160">コマンドのスコープのレベルを決定する: グローバルまたはサイトです。</span><span class="sxs-lookup"><span data-stu-id="6045b-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="6045b-161">グローバル</span><span class="sxs-lookup"><span data-stu-id="6045b-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="6045b-162">呼び出しデータ コネクタを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6045b-162">Disable Call Data Connector</span></span>

<span data-ttu-id="6045b-163">データの電話コネクタを無効にすることが関連付けを解除できませんから、フロント エンド プール、監視ストアとはそれをアンインストールまたはそれ以外の場合、バックエンドの監視データベースに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="6045b-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="6045b-164">データの電話コネクタを無効にすると、ビジネスのサーバーの呼び出しのデータをクラウドにアップロードできない Skype を停止します。</span><span class="sxs-lookup"><span data-stu-id="6045b-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="6045b-165">データの電話コネクタを無効にするには、Business Server 管理シェルには、Skype 内からセット CsCloudCallDataConnectorConfiguration コマンドレットを使用しています。</span><span class="sxs-lookup"><span data-stu-id="6045b-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="6045b-166">たとえば、次のコマンドでは、$False に EnableCallDataConnector プロパティを設定することでグローバル スコープでデータの電話コネクタを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6045b-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="6045b-167">クラウドへの呼び出しのデータのアップロードを再開する場合は、次の例のように、$True に、EnableCallDataConnector プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6045b-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="6045b-168">ビュー設置オンライン ダッシュ ボードを使用してデータ</span><span class="sxs-lookup"><span data-stu-id="6045b-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="6045b-169">データ コネクタの呼び出しを有効にすると、[品質の低下をトラブルシューティングするのにを呼び出して分析機能の使用](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)で説明するよう呼び出し分析ダッシュ ボードの設置型の呼び出しデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6045b-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="6045b-170">関連情報</span><span class="sxs-lookup"><span data-stu-id="6045b-170">For more information</span></span>

<span data-ttu-id="6045b-171">コマンドレットの詳細については、ビジネス サーバー管理シェルには、Skype からヘルプを表示コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6045b-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="6045b-172">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6045b-172">For example:</span></span>

<span data-ttu-id="6045b-173">Get-CsCloudCallDataConnector のヘルプを表示 |もっとその</span><span class="sxs-lookup"><span data-stu-id="6045b-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="6045b-174">セット-CsCloudCallDataConnector-ヘルプを表示 |もっとその</span><span class="sxs-lookup"><span data-stu-id="6045b-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="6045b-175">セット-CsCloudCallDataConnectorConfiguration-ヘルプを表示 |もっとその</span><span class="sxs-lookup"><span data-stu-id="6045b-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>