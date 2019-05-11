---
title: Skype for Business Server 2015 での集中ログ サービス プロバイダーの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: '概要: ビジネス サーバー 2015 の Skype での集中ログ サービス シナリオのプロバイダーを構成する方法を説明します。'
ms.openlocfilehash: 21c72e07365030f5bf016e4255acbf717d18a516
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914969"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での集中ログ サービス プロバイダーの構成
 
**の概要:** ビジネス サーバー 2015 の Skype での集中ログ サービス シナリオのプロバイダーを構成する方法について説明します。
  
概念とログの集中管理サービスのプロバイダーの構成を把握する最も重要なは。 Theproviders は、Skype のビジネス サーバー トレース モデルの Skype のビジネス サーバー サーバー ロールのコンポーネントに直接マップします。 プロバイダーでは、ビジネス サーバー 2015 トレースは、収集、およびフラグ (たとえば、TF_Connection または TF_Diag) の例では、致命的、エラー、または警告) メッセージの種類は、Skype のコンポーネントを定義します。 プロバイダーは、ビジネスのサーバーのサーバー ロールの各 Skype でトレース可能なコンポーネントです。 プロバイダーを使用して、コンポーネントに対するトレースのレベルと種類 (S4、SIPStack、IM、プレゼンスなど) を定義します。 定義済みのプロバイダーは、シナリオの中で特定の問題状況に対応する特定の論理コレクション用のすべてのプロバイダーをグループ化するために使用されます。
  
ビジネス サーバー管理シェルには、Skype を使用してログ サービスの集中管理機能を実行するには、CsAdministrator または CsServerAdministrator の役割に基づくアクセス制御 (RBAC) セキュリティ グループ、またはカスタムの RBAC の役割のいずれかのメンバーをする必要がありますがこれら 2 つのグループのいずれかが含まれています。 すべてのリストを取得するのにはこのコマンドレットは、(自分で作成したカスタムの RBAC の役割を含む) に割り当てられている役割に基づくアクセス制御 (RBAC) 役割次のコマンドを実行、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のプロンプト:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

次に例を示します。
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

このトピックの残りの部分では、プロバイダーの定義は、プロバイダーを変更する方法と、トラブルシューティングを最適化するためにプロバイダーの定義が含まれて焦点を当てています。 ログ サービスの一元的なコマンドを実行する 2 つの方法があります。 Business Server 2015\CLSAgent ディレクトリ C:\Program ファイル Files\Skype では、既定で配置されている CLSController.exe を使用することができます。 または、Windows PowerShell コマンドを実行するビジネス サーバー管理シェルの Skype を使用することができます。 Windows PowerShell を使用すると、ログ ・ セッションで使用するための新しいプロバイダーを定義して、その作成を完全に制御がある、収集し、どのようなレベルでデータを収集しました。
  
> [!IMPORTANT]
> 前述したように、プロバイダーは非常に強力です。ただし、シナリオは、プロバイダーが表すコンポーネントに対するトレースの設定と実行を行うために必要な具体的な情報をすべて含んでいるため、プロバイダーよりも強力です。シナリオとプロバイダーのコレクションは、大まかに言うと、大量の情報を収集する多数のコマンドを含むバッチ ファイルを実行することと、多数のコマンドをコマンド ラインから一度に 1 つずつ発行することに相当します。 
  
代わりにプロバイダーの詳細を深く掘り下げて、集中ログ サービスが既に定義されているシナリオの数、提供されます。 用意されているシナリオを使用して、遭遇する可能性がある問題の大部分に対応できます。 まれに、プロバイダーを作成して定義し、シナリオに割り当てなければならない場合があります。 新しいプロバイダーとシナリオを作成する必要があるかどうかを考慮する前に、用意されている各シナリオを十分に調べることを強くお勧めします。 ここでは、シナリオでのプロバイダー要素の使用によるトレース情報の収集方法を理解するために、プロバイダーの作成に関する情報が提示されていますが、プロバイダーそのものの詳細については説明しません。 
  
シナリオで使用するプロバイダーを定義することの重要な要素は、[ビジネス 2015年の Skype のログ サービスの一元管理](centralized-logging-service.md)の導入します。
  
- **プロバイダー**OCSLogger を理解する場合は、プロバイダーはトレース エンジンからのログを収集する必要があります OCSLogger を確認する選択したコンポーネントです。 プロバイダーは、同じコンポーネントし、多くの場合 OCSLogger で、コンポーネントと同じ名前があります。 プロバイダー サーバー ロールは、OCSLogger に慣れていない場合、一元的なログ サービスを収集できる特定のコンポーネントからログに記録します。 集中ログ サービスの場合、CLSAgent は、集中ログ サービスのプロバイダーの構成で定義したコンポーネントのトレースを行っているアーキテクチャの一部です。
    
- **ログ出力のレベル**OCSLogger には、収集したデータの詳細レベルの番号を選択するオプションが用意されています。 この機能は、ログ サービスの集中化とシナリオでは、不可欠な要素であり、**型**パラメーターによって定義されます。 次の中から選択できます。
    
  - **すべて**収集では、定義されたプロバイダーの型の致命的なメッセージ、エラー、警告、詳細、およびデバッグ情報をログをトレースします。
    
  - **致命的です**致命的なエラーです"として定義されているトレース メッセージのみを収集します
    
  - **エラー**収集のみにメッセージをトレース定義として、「エラー」または"致命的なエラーです。
    
  - **警告**「警告」、「エラー」と「致命的な」型のメッセージをトレースのみを収集します。
    
  - **情報**定義済みのプロバイダーでは、および致命的な情報メッセージ、エラー、および警告メッセージを示すトレース メッセージのみを収集します。
    
  - **詳細**型致命的、エラー、警告、および定義されたプロバイダーの詳細のすべてのトレース メッセージを収集します。
    
  - **デバッグ**のと同じでは基本的には、この 'すべて' - 致命的なエラー、エラー、警告、情報、詳細、およびデバッグの種類のトレースを収集します定義されているプロバイダーの。
    
- **フラグ**OCSLogger には、プロバイダーごとに、トレース ファイルから取得する情報の種類を定義するフラグを選択するオプションが用意されています。 プロバイダーに基づいて、次のフラグを選択したことができます。
    
  - **TF_Connection**接続に関連するログ エントリを提供します。 これらのログには、特定のコンポーネントとの間に確立された接続に関する情報が含まれます。 ネットワーク レベルの重要な情報もあります (つまり、接続の概念のないコンポーネントの)。
    
  - **TF_Security**セキュリティに関連するすべてのイベント] の [ログ エントリを提供します。 たとえば、SipStack、これらはドメイン検証エラー、およびクライアント認証の失敗などのセキュリティ イベントです。
    
  - **TF_Diag**診断したり、コンポーネントのトラブルシューティングに使用できる診断イベントを提供します。 たとえば、SipStack、これらは証明書のエラー、または DNS の警告、エラーです。
    
  - **TF_Protocol**コミュニティ コーデック パックを組み合わせて、SIP メッセージのようなプロトコル メッセージを提供します。
    
  - **TF_Component**プロバイダーの一部として指定されているコンポーネントのログ記録を有効にします。
    
  - **すべて**プロバイダーの使用可能なすべての使用可能なフラグを設定します。
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>既存のログ サービスの一元的なシナリオのプロバイダーに関する情報を確認するのには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 既存のプロバイダーの構成をレビューするには、次を入力します。
    
   ```
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    たとえば、グローバル会議アテンダントに関する情報をレビューするには、次のように入力します。
    
   ```
   Get-CsClsScenario -Identity "global/CAA"
   ```

    このコマンドは、関連するフラグ、設定、およびコンポーネントと共にプロバイダーの一覧を表示します。 表示される情報は十分なまたは既定の Windows PowerShell の書式の一覧が長すぎます、さまざまな出力メソッドを定義することによって追加情報を表示します。 これを行うには、次のように入力します。
    
   ```
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    このコマンドの出力では、各プロバイダーを行分割形式で表示します。プロバイダー名、ログの種類、ログ レベル、フラグ、GUID、および役割が行ごとに表示されます。 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>新しいログ サービスの一元的なシナリオのプロバイダーを定義するのには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. シナリオ プロバイダーは、トレースするコンポーネント、使用するフラグ、および収集する詳細レベルで構成されます。これを実行するには次のように入力します。
    
   ```
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    たとえば、Lyss プロバイダーから収集する内容および詳細レベルを定義するトレース プロバイダー定義は、次のようになります。
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

-レベルの収集致命的、エラー、警告、および情報メッセージです。 使用するフラグ Lyss プロバイダー用に定義されているは、TF_Connection、TF_Diag および $LyssProvider 変数が定義されている TF_Protocol.After、Lyss プロバイダーからのトレースを収集するために**新規 CsClsScenario**コマンドレットを使用できます。 このプロバイダーの作成と新しいシナリオへの割り当てを完了するには、次のように入力します。

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

$LyssProvider は、**New-CsClsProvider** で作成された定義済みのシナリオを含む変数です。
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>既存のログ サービスの一元的なシナリオのプロバイダーを変更するのには

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
    
2. 用意されているコマンドレットを使用して、既存のプロバイダーの更新と新しいプロバイダーの作成を実行できます。 プロバイダーを削除するには、**Set-CsClsScenario** に対して Provider パラメーター用の Replace ディレクティブを使用する必要があります。 プロバイダーを完全に削除する唯一の方法は、Update ディレクティブを使用して、削除するプロバイダーを、再定義した同じ名前のプロバイダーに置き換えることです。 たとえば、プロバイダー LyssProvider では、ログの種類として WPP、レベルとして Debug、およびフラグとして TF_CONNECTION と TF_DIAG が定義されています。 フラグを変更する必要があります「すべて」です。 このプロバイダーを変更するには、次のように入力します。
    
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
  
[新しい-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[削除 CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[セット CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[新しい-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
