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
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533135"
---
# <a name="configure-call-data-connector"></a>呼び出しデータ コネクタを構成します。

この資料では、呼び出しデータ コネクタ - ビジネス サーバー品質の呼び出しのデータがビジネス オンライン呼び出し品質ダッシュ ボード (救難) および呼び出す分析 (CA) のツールの Skype を使用して Skype の表示を有効にする 1 つのツールセットを構成する方法について説明します。 

> [!NOTE]
> パブリック プレビュー リリースでは、分析機能の呼び出しのダッシュ ボードのみがあります。

データの電話コネクタの利点と、ロールの要件など、ハイブリッド接続のセットアップの前提条件の詳細については、[呼び出しデータ コネクタの計画](plan-call-data-connector.md)を参照してください。

## <a name="enable-monitoring"></a>監視を有効にします。
 
呼び出してデータの記録 (CDR) を構成する必要があり、プールの監視、ローカル LCSCdr および QoEMetrics データベースをフロント エンドのエクスペリエンスの品質 (QoE) データの収集それ以外の場合、呼び出しの分析と品質のダッシュ ボードを呼び出すで使用するデータを取得はありません。 前に呼び出しデータ コネクタの構成、手順両方 CDR および QoE と同様に基本的な監視を構成するのには[Skype ビジネス サーバーの展開の監視](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md)を提供します。

> [!IMPORTANT]
> フロント エンド プールの監視が有効になっていない場合は、呼び出しデータ コネクタは機能しません。

## <a name="enable-call-data-connector"></a>呼び出しデータ コネクタを有効にします。

構成をデータ コネクタの呼び出しを有効にするには、次のコマンドレットを使用します。

| コマンドレット| 説明|
| :-----------------|---------------:|
| 新しい-CsCloudCallDataConnection | オンラインでのデータ コレクターを作成し、オンラインのコマンドレットです。|
| Get CsCloudCallDataConnection | 既存のオンラインでのデータ コレクターを取得する、オンラインのコマンドレットです。|  
| Get CsCloudCallDataConnector | 新規 CsCloudCallDataConnection コマンドレットによって作成された接続情報を取得する設置型のコマンドレットです。 |
| セット CsCloudCallDataConnector | 設置型のコピーを新規 CsCloudCallDataConnection コマンドレットによって作成された接続情報を保存する設置型のコマンドレットです。 |  
| セット CsCloudCallDataConnectorConfiguration | 有効にして、コネクタを無効にするまたはスコープ レベルのカスタマイズを可能にする設置コマンドレットです。|

### <a name="configure-your-environment"></a>お客様の環境を構成します。 

オンラインでのデータ コレクターを有効にするように環境を構成するにする必要があります最初 Skype にビジネス オンライン PowerShell の管理者としてログオンします。 詳細については、[ビジネス、オンラインで Office 365 の PowerShell の Skype の管理](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)を参照してください。

ビジネス オンラインの PowerShell の Skype にログインするための 2 つの方法があります。

- (推奨される方法)、ビジネス サーバー 2019 管理シェルの Skype から
- 別の PowerShell セッションから

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>ビジネス オンライン PowerShell の Business Server 管理シェルには (推奨される方法) Skype から Skype にサインインします。

1. 最初にコネクタを有効にする場合、は、次のコマンドを実行します。

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 接続が既に存在するエラーが発生する場合は、テナントの呼び出しのデータ接続を既にが存在することを意味します。 この例では、コマンドを実行します。 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>ビジネス オンライン PowerShell の別の PowerShell セッション (省略可能なメソッド) から Skype にサインインします。

1.  最初にコネクタを有効にする場合、は、次のコマンドを実行します。 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  接続が既に存在するエラーが発生する場合は、テナントの呼び出しのデータ接続を既にが存在することを意味します。 この例では、コマンドを実行します。 

    ```
    Get-CsCloudCallDataConnection  
    ```

上記のコマンドの出力には、次のように、オンプレミスの環境を構成するときに必要なトークンの値が含まれています。

Business Server 管理シェルには、Skype 内で次のコマンドを指定します。

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>スコープを構成します。

有効にできますデータ コネクタを呼び出して、特定のサイト、または、全体の Skype ビジネス サーバー配置の Business Server 管理シェルには、Skype 内からセット CsCloudCallDataConnectorConfiguration コマンドレットを使用しています。 たとえば、次のコマンドは、グローバル スコープでのデータ コネクタの呼び出しを有効にします。

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

グローバルの設定では、データの電話コネクタの構成設定はサイト スコープに割り当てられます。 監視する際に、追加の管理の柔軟性を提供します。 たとえば、管理者は、レドモンド サイトのデータ コネクタの呼び出しの転送を有効にするが、ダブリンのサイトのデータ コネクタの呼び出しの転送を無効にする例を次に示すように。

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。 たとえば、データ コネクタの呼び出しの転送がグローバル スコープで有効になっているが、(レドモンド サイトの) サイトのスコープで無効にします。 その手段の詳細記録と QoE の情報を呼び出すは、レドモンド サイトのユーザーには転送されません。 ただし、他のサイト (レドモンド サイトの設定ではなくグローバル設定によって管理されているユーザー) のユーザーは、通話の詳細記録と QoE の情報が転送されるがあります。

データ コネクタの呼び出しで使用される最も一般的に使用される設定の値は、次の表のとおりです。  

|プロパティ|説明|既定値|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |データの電話コネクタが有効になっているかどうかを示します。 True の場合、オンラインでの監視を監視レコードが転送されます。  <br/> |$False  <br/> |
| ID  | コマンドのスコープのレベルを決定する: グローバルまたはサイトです。   | グローバル  |

## <a name="disable-call-data-connector"></a>呼び出しデータ コネクタを無効にします。

データの電話コネクタを無効にすることが関連付けを解除できませんから、フロント エンド プール、監視ストアとはそれをアンインストールまたはそれ以外の場合、バックエンドの監視データベースに影響を与えます。 データの電話コネクタを無効にすると、ビジネスのサーバーの呼び出しのデータをクラウドにアップロードできない Skype を停止します。 

データの電話コネクタを無効にするには、Business Server 管理シェルには、Skype 内からセット CsCloudCallDataConnectorConfiguration コマンドレットを使用しています。 たとえば、次のコマンドでは、$False に EnableCallDataConnector プロパティを設定することでグローバル スコープでデータの電話コネクタを無効にします。

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

クラウドへの呼び出しのデータのアップロードを再開する場合は、次の例のように、$True に、EnableCallDataConnector プロパティを設定します。

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>ビュー設置オンライン ダッシュ ボードを使用してデータ

 データ コネクタの呼び出しを有効にすると、[品質の低下をトラブルシューティングするのにを呼び出して分析機能の使用](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)で説明するよう呼び出し分析ダッシュ ボードの設置型の呼び出しデータを表示できます。


## <a name="for-more-information"></a>関連情報

コマンドレットの詳細については、ビジネス サーバー管理シェルには、Skype からヘルプを表示コマンドを使用できます。 次に例を示します。

Get-CsCloudCallDataConnector のヘルプを表示 |もっとその

セット-CsCloudCallDataConnector-ヘルプを表示 |もっとその

セット-CsCloudCallDataConnectorConfiguration-ヘルプを表示 |もっとその