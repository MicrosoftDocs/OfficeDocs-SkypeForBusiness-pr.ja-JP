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
ms.localizationpriority: medium
ms.collection: ''
description: 通話データ コネクタを構成する手順。これにより、Skype for BusinessオンプレミスのテレメトリをSkype for Business Online ツールを使用して表示できます。
ms.openlocfilehash: 0d92d31798cd4b3fb5a1b4c555ff0ff00c2bdf31
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156935"
---
# <a name="configure-call-data-connector"></a>通話データ コネクタの構成

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


この記事では、通話データ コネクタを構成する方法について説明します。これは、Microsoft 通話品質ダッシュボード (CQD) ツールと Call Analytics (CA) ツールを使用してSkype for Business Server通話品質データを表示できるようにする単一のツールセットです。

通話データ コネクタの利点と前提条件 (ロール要件やハイブリッド接続の設定など) の詳細については、「 [通話データ コネクタの計画](plan-call-data-connector.md)」を参照してください。

## <a name="enable-monitoring"></a>監視を有効にする
 
ローカル LCSCdr データベースと QoEMetrics データベースを使用して、フロントエンド プールの監視で通話データ記録 (CDR) と Quality of Experience (QoE) データ収集を構成する必要があります。それ以外の場合、Call Analytics と通話品質ダッシュボードは、操作するデータを取得しません。 通話データ コネクタを構成する前に、「[Skype for Business Serverに監視を展開](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md)する」の手順に従って、CDR と QoE の両方と基本的な監視を構成します。

> [!IMPORTANT]
> フロントエンド プールで監視が有効になっていない場合、データ コネクタの呼び出しは機能しません。

## <a name="enable-call-data-connector"></a>通話データ コネクタを有効にする

データ コネクタの呼び出しを構成して有効にするには、次のコマンドレットを使用します。

| コマンドレット| 説明|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | オンライン データ コレクターを確立するオンライン コマンドレット。|
| Get-CsCloudCallDataConnection | 既存のオンライン データ コレクターを取得するオンライン コマンドレット。|  
| Get-CsCloudCallDataConnector | New-CsCloudCallDataConnection コマンドレットによって作成された接続情報を取得するオンプレミスコマンドレット。 |
| Set-CsCloudCallDataConnector | New-CsCloudCallDataConnection コマンドレットによって作成された接続情報のオンプレミス コピーを保存するオンプレミスコマンドレット。 |  
| Set-CsCloudCallDataConnectorConfiguration | コネクタを有効または無効にしてスコープ レベルをカスタマイズできるオンプレミスコマンドレット。|

> [!NOTE]
> 構成を消去して最初からやり直すには、Remove-csclouddatconnectorconfiguration コマンドレットを使用してください。

### <a name="configure-your-environment"></a>環境を構成する 

オンライン データ コレクターを有効にするように環境を構成するには、最初に管理者として PowerShell モジュールMicrosoft Teamsログインする必要があります。 詳細については、 [PowerShell の概要Microsoft Teams](/microsoftteams/teams-powershell-overview)参照してください。

Microsoft Teams PowerShell モジュールにログインするには、次の 2 つの方法があります。

- Skype for Business Server 2019 管理シェルから (推奨される方法)
- 別の PowerShell セッションから

#### <a name="log-in-to-microsoft-teams-powershell-module-from-the-skype-for-business-server-management-shell-recommended-method"></a>Skype for Business Server管理シェルから PowerShell モジュールMicrosoft Teamsにログインします (推奨される方法)

1. コネクタを初めて有効にする場合は、次のコマンドを実行します。

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 接続が既に存在するというエラーが発生した場合は、呼び出しデータ接続がテナントに対して既に存在することを意味します。 この場合は、次のコマンドを実行します。 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-microsoft-teams-powershell-module-from-another-powershell-session-optional-method"></a>別の PowerShell セッションから PowerShell モジュールMicrosoft Teamsにログインする (オプションの方法)

1.  コネクタを初めて有効にする場合は、次のコマンドを実行します。 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  接続が既に存在するというエラーが発生した場合は、呼び出しデータ接続がテナントに対して既に存在することを意味します。 この場合は、次のコマンドを実行します。 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

上記のコマンドの出力には、次のようにオンプレミス環境を構成するときに必要なトークン値が含まれています。

Skype for Business Server管理シェル内から、次のコマンドを指定します。

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>スコープの構成

Skype for Business Server管理シェル内からSet-CsCloudCallDataConnectorConfiguration コマンドレットを使用して、特定のサイトまたはSkype for Business Server展開全体に対して Call Data Connector を有効にすることができます。 たとえば、次のコマンドを使用すると、グローバル スコープでデータ コネクタの呼び出しが有効になります。

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

グローバル設定に加えて、Call Data Connector 構成設定をサイト スコープに割り当てることができます。 これにより、監視に関する追加の管理柔軟性が提供されます。 たとえば、次の例に示すように、管理者は Redmond サイトの通話データ コネクタ転送を有効にし、ダブリン サイトの通話データ コネクタ転送を無効にすることができます。

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。 たとえば、データ コネクタの呼び出し転送がグローバル スコープで有効になっているが、サイト スコープ (Redmond サイトの場合) で無効になっているとします。 つまり、通話の詳細記録と QoE 情報は、Redmond サイトのユーザーには転送されません。 ただし、他のサイトのユーザー (つまり、Redmond サイト設定ではなくグローバル設定で管理されているユーザー) には、通話の詳細記録と QoE 情報が転送されます。

通話データ コネクタで使用される最もよく使用される設定の値を次の表に示します。  

|プロパティ|説明|既定値|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |データ コネクタの呼び出しが有効かどうかを示します。 True の場合、監視レコードはオンライン監視に転送されます。  <br/> |$False  <br/> |
| ID | コマンドのスコープ レベル (グローバルまたはサイト) を決定します。   | グローバル  |

## <a name="disable-call-data-connector"></a>通話データ コネクタを無効にする

通話データ コネクタを無効にしても、監視ストアとフロントエンド プールの関連付けが解除されることはなく、バックエンド監視データベースをアンインストールしたり、それ以外の場合に影響を与えたりすることはありません。 通話データ コネクタを無効にすると、Skype for Business Serverが通話データをクラウドにアップロードできなくなります。 

Skype for Business Server管理シェル内から Set-CsCloudCallDataConnectorConfiguration コマンドレットを使用して、データ コネクタの呼び出しを無効にします。 たとえば、次のコマンドでは、EnableCallDataConnector プロパティを$Falseに設定することで、グローバル スコープでデータ コネクタの呼び出しを無効にします。

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

クラウドへの呼び出しデータのアップロードを再開する場合は、次の例に示すように EnableCallDataConnector プロパティを$Trueに戻します。

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>オンライン ダッシュボードを使用してオンプレミス のデータを表示する

 通話データ コネクタが有効になると、通話分析ダッシュボードまたは通話品質ダッシュボードでオンプレミスの通話データを表示できます。[「通話分析を使用して品質の低いトラブルシューティングを行い](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)、通話[品質ダッシュボードをオンにして、通話品質ダッシュボードをオンにして、Microsoft TeamsおよびオンラインSkype for Business](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)します。

## <a name="for-more-information"></a>詳細情報

コマンドレットの詳細については、Skype for Business Server Management Shell のGet-Help コマンドを使用できます。 以下に例を示します。

Get-Help Get-CsCloudCallDataConnector |もっとその

Get-Help Set-CsCloudCallDataConnector |もっとその

Get-Help Set-CsCloudCallDataConnectorConfiguration |もっとその
