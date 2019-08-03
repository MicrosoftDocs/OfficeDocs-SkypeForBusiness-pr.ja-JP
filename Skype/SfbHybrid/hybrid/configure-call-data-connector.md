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
ms.openlocfilehash: 1851e1e0c430107a27d706f7bc16ad974c5abaed
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2019
ms.locfileid: "36160669"
---
# <a name="configure-call-data-connector"></a>通話データコネクタを構成する

この記事では、Skype for Business Online 通話品質ダッシュボード (CQD) およびコール分析 (CA) ツールを使用して Skype for business Server の通話品質データを表示できるようにする単一のツールセットを、通話データコネクタを構成する方法について説明します。 

> [!NOTE]
> パブリックプレビューリリースでは、通話分析のダッシュボードのみを使用できます。

コールデータコネクタの利点と前提条件 (ロール要件、ハイブリッド接続の設定など) の詳細については、「 [Plan Call Data connector](plan-call-data-connector.md)」を参照してください。

## <a name="enable-monitoring"></a>監視を有効にする
 
ローカルの LCSCdr および QoEMetrics データベースを使用して、コールデータ記録 (CDR) と QoE (Quality of Experience) データ収集をフロントエンドプールの監視に構成する必要があります。それ以外の場合、通話分析と通話品質ダッシュボードは、使用するデータを取得しません。 通話データコネクタを構成する前に、「 [Deploy monitoring In Skype For Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) 」に記載されている手順に従って、CDR と qoe の両方および基本的な監視を構成します。

> [!IMPORTANT]
> フロントエンドプールで監視が有効になっていない場合、Call Data Connector は機能しません。

## <a name="enable-call-data-connector"></a>通話データコネクタを有効にする

Call Data Connector を構成して有効にするには、次のコマンドレットを使用します。

| コマンドレット| 説明|
| :-----------------|---------------:|
| CsCloudCallDataConnection | オンラインデータコレクターを確立するオンラインコマンドレット。|
| CsCloudCallDataConnection | 既存のオンラインデータコレクターを取得するオンラインコマンドレット。|  
| CsCloudCallDataConnector | CsCloudCallDataConnection コマンドレットによって作成された接続情報を取得するオンプレミスのコマンドレットです。 |
| CsCloudCallDataConnector | CsCloudCallDataConnection コマンドレットによって作成された接続情報のオンプレミスコピーを保存するオンプレミスのコマンドレットです。 |  
| CsCloudCallDataConnectorConfiguration | コネクタを有効または無効にして、スコープレベルをカスタマイズできるオンプレミスのコマンドレット。|

> [!NOTE]
> 構成を消去して最初からやり直すには、「Remove-csclouddatコネクタ構成コマンドレット」を使用してください。

### <a name="configure-your-environment"></a>環境を構成する 

オンラインデータコレクターを有効にするように環境を構成するには、まず、管理者として Skype for Business Online PowerShell にログインする必要があります。 詳細については、「 [Office 365 PowerShell を使用して Skype For Business Online を管理](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)する」を参照してください。

Skype for Business Online PowerShell にログインするには、次の2つの方法があります。

- Skype for Business Server 2019 管理シェル (推奨される方法)
- 別の PowerShell セッションから

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Skype for business Server 管理シェルからの Skype for Business Online PowerShell へのログイン (推奨方法)

1. コネクタを初めて有効にする場合は、次のコマンドを実行します。

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 接続が既に存在することを示すエラーが表示された場合は、テナントの通話データ接続が既に存在することを意味します。 この場合は、次のコマンドを実行します。 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>別の PowerShell セッションからの Skype for Business Online PowerShell へのログイン (オプションのメソッド)

1.  コネクタを初めて有効にする場合は、次のコマンドを実行します。 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  接続が既に存在することを示すエラーが表示された場合は、テナントの通話データ接続が既に存在することを意味します。 この場合は、次のコマンドを実行します。 

    ```
    Get-CsCloudCallDataConnection  
    ```

上記のコマンドの出力には、次のようにオンプレミス環境を構成するときに必要になるトークン値が含まれています。

Skype for Business Server 管理シェルで、次のコマンドを指定します。

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>スコープを構成する

Skype for Business Server 管理シェル内から CsCloudCallDataConnectorConfiguration コマンドレットを使用して、特定のサイトまたは Skype for Business Server の展開全体に対して、Call Data Connector を有効にできます。 たとえば、次のコマンドを実行すると、グローバルスコープで呼び出しデータコネクタが有効になります。

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

グローバル設定に加えて、通話データコネクタの構成設定をサイトスコープに割り当てることができます。 これにより、監視に関してさらに管理の柔軟性が得られます。 たとえば、管理者は、次の例に示されているように、Redmond サイトに対して通話データコネクタ転送を有効にして、ダブリンサイトの通話データコネクタ転送を無効にすることができます。

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。 たとえば、通話データコネクタ転送がグローバルスコープで有効になっていても、サイトスコープ (Redmond サイトの場合) で無効になっているとします。 これは、Redmond サイトのユーザーに対して、通話詳細記録と QoE 情報が転送されないことを意味します。 ただし、他のサイトのユーザー (つまり、Redmond サイト設定ではなくグローバル設定で管理されているユーザー) には、通話詳細記録と QoE 情報が転送されます。

次の表に、Call Data Connector で使用される最も一般的に使用される設定の値を示します。  

|プロパティ|説明|既定値|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |通話データコネクタが有効かどうかを示します。 True の場合、監視レコードはオンライン監視に転送されます。  <br/> |$False  <br/> |
| ID | コマンドのスコープレベルを指定します (グローバルまたはサイト)。   | 全体  |

## <a name="disable-call-data-connector"></a>通話データコネクタを無効にする

通話データコネクタを無効にしても、監視ストアとフロントエンドプールの関連付けは解除されません。また、その他のバックエンド監視データベースに影響を与えることもありません。 通話データコネクタを無効にすると、Skype for Business Server が通話データをクラウドにアップロードするのを停止します。 

通話データコネクタを無効にするには、Skype for Business Server 管理シェルで CsCloudCallDataConnectorConfiguration コマンドレットを使用します。 たとえば、次のコマンドを実行すると、EnableCallDataConnector プロパティを $False に設定することによって、グローバルスコープの通話データコネクタが無効になります。

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

呼び出しデータのクラウドへのアップロードを再開する場合は、次の例に示すように、EnableCallDataConnector プロパティを $True に戻します。

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>オンラインダッシュボードを使用してオンプレミスデータを表示する

 Call Data Connector が有効になったら、「[通話分析を使用して品質低下のトラブルシューティングを行う](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)」で説明されているように、通話分析のダッシュボードでオンプレミスの通話データを表示できます。


## <a name="for-more-information"></a>関連情報

コマンドレットの詳細については、「Skype for Business Server 管理シェル」の「Get-help」コマンドを使用できます。 次に例を示します。

Get-help get-help CsCloudCallDataConnector |もっとその

Get-help CsCloudCallDataConnector |もっとその

Get-help CsCloudCallDataConnectorConfiguration |もっとその
