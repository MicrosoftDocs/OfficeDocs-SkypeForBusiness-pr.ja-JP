---
title: Skype for Business Server 2015 での集中ログ サービス プロバイダーの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: '概要: Skype for Business Server 2015 の一元管理ログサービスのシナリオプロバイダーを構成する方法について説明します。'
ms.openlocfilehash: a9987d99b2caf00acc92de92a8d997845ad8f921
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274451"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での集中ログ サービス プロバイダーの構成
 
**概要:** Skype for Business Server 2015 の中央集中ログサービスのシナリオプロバイダーを構成する方法について説明します。
  
一元管理サービスのプロバイダーの概念と構成は、理解するうえで最も重要なものの1つです。 このプロバイダーは、Skype for Business Server のトレースモデルに含まれている Skype for Business Server の役割コンポーネントに直接マップされます。 プロバイダーは、トレースされる Skype for Business Server 2015 のコンポーネント、収集するメッセージの種類 (たとえば、致命的、エラー、警告)、フラグ (TF_Connection や TF_Diag など) を定義します。これは、 プロバイダーは、各 Skype for Business Server server の役割の追跡可能なコンポーネントです。 プロバイダーを使用して、コンポーネントに対するトレースのレベルと種類 (S4、SIPStack、IM、プレゼンスなど) を定義します。 定義済みのプロバイダーは、シナリオの中で特定の問題状況に対応する特定の論理コレクション用のすべてのプロバイダーをグループ化するために使用されます。
  
Skype for Business Server 管理シェルを使用して一元的なログサービス機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、または、次の2つのグループのいずれかが含まれます。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Skype for Business Server 管理シェルまたは Windows PowerShell で次のコマンドを実行します。プロンプト
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

次に例を示します。
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

このトピックの残りの部分では、トラブルシューティングを最適化するために、プロバイダーの定義方法、プロバイダーの変更方法、プロバイダー定義に含まれる内容について説明します。 一元化されたログサービスのコマンドを発行するには、2つの方法があります。 既定では、directory C:\Program Files\Common Files\Skype for Business Server 2015 \ Clscontroller に含まれる CLSController を使用できます。 または、Skype for Business Server 管理シェルを使用して、Windows PowerShell コマンドを発行することもできます。 Windows PowerShell を使用すると、ログセッションで使用するために新しいプロバイダーを定義することができます。また、それらの作成、収集内容、データ収集のレベルなども完全に制御できます。
  
> [!IMPORTANT]
> 前述したように、プロバイダーは非常に強力です。ただし、シナリオは、プロバイダーが表すコンポーネントに対するトレースの設定と実行を行うために必要な具体的な情報をすべて含んでいるため、プロバイダーよりも強力です。シナリオとプロバイダーのコレクションは、大まかに言うと、大量の情報を収集する多数のコマンドを含むバッチ ファイルを実行することと、多数のコマンドをコマンド ラインから一度に 1 つずつ発行することに相当します。 
  
プロバイダーの詳細を深く把握する必要はありませんが、一元管理サービスには、既に定義されている多数のシナリオが用意されています。 用意されているシナリオを使用して、遭遇する可能性がある問題の大部分に対応できます。 まれに、プロバイダーを作成して定義し、シナリオに割り当てなければならない場合があります。 新しいプロバイダーとシナリオを作成する必要があるかどうかを考慮する前に、用意されている各シナリオを十分に調べることを強くお勧めします。 ここでは、シナリオでのプロバイダー要素の使用によるトレース情報の収集方法を理解するために、プロバイダーの作成に関する情報が提示されていますが、プロバイダーそのものの詳細については説明しません。 
  
[Skype For business 2015 の中央集中ログサービス](centralized-logging-service.md)で導入された、シナリオで使用するプロバイダーを定義する主な要素は次のとおりです。
  
- **Providers**OCSLogger に精通している場合、プロバイダーは、トレースエンジンがログを収集する必要があることを OCSLogger に伝えるために選ぶコンポーネントです。 プロバイダーは同じコンポーネントであり、多くの場合、OCSLogger のコンポーネントと同じ名前が付いています。 OCSLogger に精通していない場合は、一元管理サービスでログを収集できるのは、サーバーの役割固有のコンポーネントです。 一元管理サービスの場合、CLSAgent は、プロバイダー構成で定義したコンポーネントのトレースを実行している一元ログサービスのアーキテクチャ部分です。
    
- **ログレベル**OCSLogger では、収集されたデータの詳細レベルの数を選択するオプションを提供しました。 この機能は、一元ログサービスとシナリオの一部であり、 **Type**パラメーターによって定義されます。 次のいずれかを選ぶことができます。
    
  - **すべて**Fatal、error、warning、verbose、debug の各情報型のトレースメッセージを、定義されたプロバイダーのログに収集します。
    
  - **Fatal**"致命的" として定義されているトレースメッセージのみを収集します。
    
  - **エラー**"Error" または "Fatal" として定義されているトレースメッセージのみを収集します。
    
  - **警告**"警告"、"エラー"、"致命的" という種類のトレースメッセージのみを収集します。
    
  - **情報**定義されたプロバイダーの情報メッセージを示すトレースメッセージと、致命的、エラー、および警告メッセージだけを収集します。
    
  - **Verbose**定義されたプロバイダーの fatal、error、warning、verbose という種類のすべてのトレースメッセージを収集します。
    
  - **Debug**これは基本的に "All" と同等です。これは、定義されたプロバイダーの致命的、エラー、警告、Info、Verbose、Debug の種類のトレースを収集します。
    
- **フラグ**OCSLogger では、トレースファイルから取得できる情報の種類を定義したプロバイダーごとに、フラグを選択するオプションが提供されました。 プロバイダーに基づいて、次のフラグを選ぶことができます。
    
  - **TF_Connection**接続に関連するログエントリを提供します。 これらのログには、特定のコンポーネントとの間で確立された接続に関する情報が含まれます。 これには、重要なネットワークレベルの情報が含まれることもあります (つまり、接続の概念なし)。
    
  - **TF_Security**セキュリティに関連するすべてのイベントとログエントリを提供します。 たとえば、SipStack の場合、これは、ドメイン検証エラー、クライアント認証、承認エラーなどのセキュリティイベントです。
    
  - **TF_Diag**コンポーネントの診断またはトラブルシューティングに使用できる診断イベントを提供します。 たとえば、SipStack の場合は、証明書のエラー、DNS の警告/エラーがあります。
    
  - **TF_Protocol**SIP、結合されたコミュニティコーデックパックメッセージなどのプロトコルメッセージを提供します。
    
  - **TF_Component**プロバイダーの一部として指定されたコンポーネントのログの記録を有効にします。
    
  - **すべて**プロバイダーで利用可能なすべてのフラグを設定します。
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>既存の集中ログサービスシナリオプロバイダーに関する情報を確認するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 既存のプロバイダーの構成をレビューするには、次を入力します。
    
   ```
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    たとえば、グローバル会議アテンダントに関する情報をレビューするには、次のように入力します。
    
   ```
   Get-CsClsScenario -Identity "global/CAA"
   ```

    このコマンドは、関連するフラグ、設定、およびコンポーネントと共にプロバイダーの一覧を表示します。 表示された情報が不足している場合、または既定の Windows PowerShell リスト形式でリストが長すぎる場合は、別の出力メソッドを定義して追加の情報を表示できます。 これを行うには、次のように入力します。
    
   ```
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    このコマンドの出力では、各プロバイダーを行分割形式で表示します。プロバイダー名、ログの種類、ログ レベル、フラグ、GUID、および役割が行ごとに表示されます。 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>新しい集中ログサービスシナリオプロバイダーを定義するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. シナリオ プロバイダーは、トレースするコンポーネント、使用するフラグ、および収集する詳細レベルで構成されます。これを実行するには次のように入力します。
    
   ```
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    たとえば、Lyss プロバイダーから収集する内容および詳細レベルを定義するトレース プロバイダー定義は、次のようになります。
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

レベルは、致命的、エラー、警告、および情報メッセージを収集します。 使用されるフラグは、TF_Connection、TF_Diag、TF_Protocol に定義されているすべてのフラグです。変数 $LyssProvider を定義した後は、**新しい-CsClsScenario**コマンドレットを使用して、a ss provider からトレースを収集することができます。 このプロバイダーの作成と新しいシナリオへの割り当てを完了するには、次のように入力します。

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

$LyssProvider は、**New-CsClsProvider** で作成された定義済みのシナリオを含む変数です。
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>既存の集中ログサービスシナリオプロバイダーを変更するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 既存のプロバイダーの構成を更新または変更するには、次のように入力します。
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    次のように入力することで、プロバイダーを割り当てるシナリオを更新します。
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

コマンドを実行すると、最終的にシナリオ site:Redmond/RedmondLyssInfo のフラグと割り当てられるプロバイダーのレベルが更新されます。Get-CsClsScenario を使用して、新しいシナリオを表示できます。詳細については、「[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)」を参照してください。
> [!CAUTION]
> **New-ClsCsProvider** は、フラグが有効かどうかを確認しません。 フラグのスペル (TF_DIAG、TF_CONNECTION など) が正しいことを確認してください。 フラグのスペルが正しくない場合、プロバイダーは期待されるログ情報を返すことができません。
  
このシナリオに対してプロバイダーを追加するには、次のように入力します。

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Add ディレクティブで定義される各プロバイダーは、**New-CsClsProvider** プロセスで既に定義されています。
### <a name="to-remove-a-scenario-provider"></a>シナリオ プロバイダーを削除するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 用意されているコマンドレットを使用して、既存のプロバイダーの更新と新しいプロバイダーの作成を実行できます。 プロバイダーを削除するには、**Set-CsClsScenario** に対して Provider パラメーター用の Replace ディレクティブを使用する必要があります。 プロバイダーを完全に削除する唯一の方法は、Update ディレクティブを使用して、削除するプロバイダーを、再定義した同じ名前のプロバイダーに置き換えることです。 たとえば、プロバイダー LyssProvider では、ログの種類として WPP、レベルとして Debug、およびフラグとして TF_CONNECTION と TF_DIAG が定義されています。 フラグを "すべて" に変更する必要があります。 このプロバイダーを変更するには、次のように入力します。
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. シナリオとそれに関連付けられているプロバイダーを完全に削除するには、次のように入力します。
    
   ```
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    次に例を示します。
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > **Remove-CsClsScenario** コマンドレットは、確認のプロンプトを表示しません。 シナリオは、それに関連付けられているプロバイダーと共に削除されます。 シナリオを初めて作成したときに使用したコマンドを再実行することで、シナリオを再作成できます。 削除したシナリオまたはプロバイダーを回復するための手順はありません。
  
**Remove-CsClsScenario** コマンドレットを使用してシナリオを削除すると、シナリオはスコープから完全に削除されます。 作成したシナリオとシナリオの一部であったプロバイダーを使用するには、新しいプロバイダーを作成し、それらを新しいシナリオに割り当てます。
## <a name="see-also"></a>関連項目

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[新しい CsClsScenario シナリオ](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[削除-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[新規の CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
