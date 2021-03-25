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
# <a name="configure-call-data-connector"></a>通話データ コネクタの構成

この記事では、Skype for Business Online 通話品質ダッシュボード (CQD) ツールと通話分析 (CA) ツールを使用して Skype for Business Server 通話品質データを表示できる単一のツールセットである通話データ コネクタを構成する方法について説明します。

役割要件やハイブリッド接続のセットアップなど、通話データ コネクタの利点と前提条件の詳細については [、「Plan Call Data Connector」を参照してください](plan-call-data-connector.md)。

## <a name="enable-monitoring"></a>監視を有効にする
 
ローカルの LCSCdr データベースと QoEMetrics データベースを使用して、フロントエンド プールの監視で通話データ記録 (CDR) および QoE (QoE) データ収集を構成する必要があります。それ以外の場合、Call Analytics と Call Quality ダッシュボードは、データを取得して機能しません。 通話データ コネクタを構成する前に [、「Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) での監視の展開」の手順に従って、CDR と QoE の両方と基本的な監視を構成します。

> [!IMPORTANT]
> フロントエンド プールで監視が有効になっていない場合、データ コネクタの呼び出しは機能しません。

## <a name="enable-call-data-connector"></a>通話データ コネクタを有効にする

データ コネクタの呼び出しを構成および有効にするには、次のコマンドレットを使用します。

| コマンドレット| 説明|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | オンライン データ コレクターを確立するオンライン コマンドレット。|
| Get-CsCloudCallDataConnection | 既存のオンライン データ コレクターを取得するオンライン コマンドレット。|  
| Get-CsCloudCallDataConnector | このコマンドレットによって作成された接続情報を取得するオンプレミスのコマンドレットNew-CsCloudCallDataConnectionします。 |
| Set-CsCloudCallDataConnector | オンプレミスのコマンドレットで、New-CsCloudCallDataConnection コマンドレットによって作成された接続情報のオンプレミス コピーを保存します。 |  
| Set-CsCloudCallDataConnectorConfiguration | コネクタを有効または無効にし、スコープ レベルをカスタマイズできるオンプレミスのコマンドレット。|

> [!NOTE]
> 構成を消去して最初から実行するには、Remove-csclouddatconnectorconfiguration コマンドレットを使用してください。

### <a name="configure-your-environment"></a>環境を構成する 

オンライン データ コレクターを有効にするために環境を構成するには、まず管理者として Skype for Business Online PowerShell にログインする必要があります。 詳細については [、「Manage Skype for Business Online with Office 365 PowerShell」を参照してください](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

Skype for Business Online PowerShell にログインするには、次の 2 つの方法があります。

- Skype for Business Server 2019 管理シェルから (推奨される方法)
- 別の PowerShell セッションから

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Skype for Business Server 管理シェルから Skype for Business Online PowerShell にログインする (推奨される方法)

1. コネクタを初めて有効にする場合は、次のコマンドを実行します。

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 接続が既に存在するというエラーが発生した場合は、テナントの通話データ接続が既に存在することを意味します。 この場合は、次のコマンドを実行します。 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>別の PowerShell セッションから Skype for Business Online PowerShell にログインする (オプションの方法)

1.  コネクタを初めて有効にする場合は、次のコマンドを実行します。 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  接続が既に存在するというエラーが発生した場合は、テナントの通話データ接続が既に存在することを意味します。 この場合は、次のコマンドを実行します。 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

上記のコマンドの出力にはトークン値が含まれています。この値は、次のようにオンプレミス環境を構成するときに必要になります。

Skype for Business Server 管理シェル内で、次のコマンドを指定します。

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>スコープを構成する

Skype for Business Server 管理シェル内の Set-CsCloudCallDataConnectorConfiguration コマンドレットを使用して、特定のサイトまたは Skype for Business Server 展開全体に対して通話データ コネクタを有効にできます。 たとえば、次のコマンドを使用すると、グローバル スコープでデータ コネクタの呼び出しが有効になります。

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

グローバル設定に加えて、Call Data Connector 構成設定をサイト スコープに割り当てることができます。 これにより、監視に関して管理の柔軟性が向上します。 たとえば、次の例に示すように、管理者は Redmond サイトの通話データ コネクタ転送を有効にできますが、ダブリン サイトの通話データ コネクタ転送を無効にできます。

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。 たとえば、グローバル スコープでデータ コネクタ転送の呼び出しが有効になっているが、サイト スコープ (Redmond サイトの場合) では無効になっているとします。 つまり、通話の詳細記録と QoE 情報は、Redmond サイトのユーザーに転送されません。 ただし、他のサイトのユーザー (つまり、Redmond サイト設定の代わりにグローバル設定によって管理されるユーザー) は、通話の詳細記録と QoE 情報を転送します。

通話データ コネクタで使用される最もよく使用される設定の値を次の表に示します。  

|プロパティ|説明|既定値|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |データ コネクタの呼び出しが有効かどうかを示します。 True の場合、監視レコードはオンライン監視に転送されます。  <br/> |$False  <br/> |
| ID | コマンドのスコープ レベル (グローバルまたはサイト) を決定します。   | global  |

## <a name="disable-call-data-connector"></a>通話データ コネクタを無効にする

通話データ コネクタを無効にしても、監視ストアとフロントエンド プールとの関連付けは解除されません。また、バックエンド監視データベースをアンインストールしたり、その他の影響を与える場合もありません。 通話データ コネクタを無効にすると、Skype for Business Server が通話データをクラウドにアップロードするのを停止します。 

Skype for Business Server 管理シェル内の Set-CsCloudCallDataConnectorConfigurationコマンドレットを使用して、データ コネクタの呼び出しを無効にします。 たとえば、次のコマンドは、EnableCallDataConnector プロパティを次の値に設定して、グローバル スコープでデータ コネクタの呼び出しを$False。

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

クラウドへの通話データのアップロードを再開する場合は、次の例に示すように、EnableCallDataConnector プロパティを $True に戻します。

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>オンライン ダッシュボードを使用してオンプレミス のデータを表示する

 通話データ コネクタを有効にすると、「通話分析を使用して品質の低下をトラブルシューティングし[、Microsoft Teams](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)および Skype for [](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) Business Online の通話品質ダッシュボードを有効にし、使用する」の説明に従って、通話分析ダッシュボードまたは通話品質ダッシュボードでオンプレミス通話データを表示できます。

## <a name="for-more-information"></a>詳細情報

コマンドレットの詳細については、Skype for Business Server 管理シェルGet-Helpコマンドを使用できます。 次に例を示します。

Get-Help Get-CsCloudCallDataConnector |もっとその

Get-Help Set-CsCloudCallDataConnector |もっとその

Get-Help Set-CsCloudCallDataConnectorConfiguration |もっとその