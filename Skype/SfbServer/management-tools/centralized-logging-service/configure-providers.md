---
title: Skype for Business Server 2015 で集中ログ サービスのプロバイダーを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: '概要: Skype for Business Server 2015 の集中ログ サービスのシナリオ プロバイダーを構成する方法について説明します。'
ms.openlocfilehash: cd0364d6497aa53d258b5346090d6cdd7c338cc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098853"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で集中ログ サービスのプロバイダーを構成する
 
**概要:** Skype for Business Server 2015 の集中ログ サービスのシナリオ プロバイダーを構成する方法について説明します。
  
集中ログ サービスのプロバイダーの概念と構成は、把握する最も重要な点の 1 つです。 Theproviders は、Skype for Business Server トレース モデルの Skype for Business Server サーバーの役割コンポーネントに直接マップされます。 プロバイダーは、追跡される Skype for Business Server 2015 のコンポーネント、収集するメッセージの種類 (致命的、エラー、警告など)、フラグ (TF_Connection や TF_Diag など) を定義します。 プロバイダーは、Skype for Business Server サーバーの各役割の追跡可能なコンポーネントです。 プロバイダーを使用して、コンポーネントに対するトレースのレベルと種類 (S4、SIPStack、IM、プレゼンスなど) を定義します。 定義済みのプロバイダーは、シナリオの中で特定の問題状況に対応する特定の論理コレクション用のすべてのプロバイダーをグループ化するために使用されます。
  
Skype for Business Server 管理シェルを使用して集中ログ サービス機能を実行するには、CsAdministrator または CsServerAdministrator 役割ベースのアクセス制御 (RBAC) セキュリティ グループのメンバーか、これら 2 つのグループのいずれかを含むカスタム RBAC 役割である必要があります。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割 (自分で作成したカスタム RBAC の役割を含む) の一覧を取得するには、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

次に例を示します。
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

このトピックの以下の部分では、プロバイダーの定義方法、プロバイダーの変更方法、およびトラブルシューティングを最適化するためにプロバイダー定義に含まれるものに注目します。 集中ログ サービス コマンドを発行するには、2 つの方法があります。 既定では、ディレクトリ C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent にある CLSController.exeを使用できます。 または、Skype for Business Server 管理シェルを使用して、複数のコマンドWindows PowerShellすることもできます。 このWindows PowerShellを使用すると、ログ セッションで使用する新しいプロバイダーを定義し、作成、収集する情報、およびデータを収集するレベルを完全に制御できます。
  
> [!IMPORTANT]
> 前述したように、プロバイダーは非常に強力です。ただし、シナリオは、プロバイダーが表すコンポーネントに対するトレースの設定と実行を行うために必要な具体的な情報をすべて含んでいるため、プロバイダーよりも強力です。シナリオとプロバイダーのコレクションは、大まかに言うと、大量の情報を収集する多数のコマンドを含むバッチ ファイルを実行することと、多数のコマンドをコマンド ラインから一度に 1 つずつ発行することに相当します。 
  
プロバイダーの詳細を深く掘り下げる必要が生じなくても、集中ログ サービスには、既に定義されている多数のシナリオが提供されます。 用意されているシナリオを使用して、遭遇する可能性がある問題の大部分に対応できます。 まれに、プロバイダーを定義してシナリオに割り当てなければならない場合があります。 新しいプロバイダーとシナリオを作成する必要があるかどうかを考慮する前に、用意されているシナリオを十分に調べることを強くお勧めします。 ここでは、シナリオでのプロバイダー要素の使用によるトレース情報の収集方法を理解するために、プロバイダーの作成に関する情報が提示されていますが、プロバイダーそのものの詳細については説明しません。 
  
[Skype for Business 2015](centralized-logging-service.md)の集中ログ サービスで導入された、シナリオで使用するプロバイダーを定義する重要な要素は次のとおりです。
  
- **プロバイダー** OCSLogger に精通している場合、プロバイダーは、トレース エンジンがログを収集する必要がある情報を OCSLogger に伝えるコンポーネントです。 プロバイダーは同じコンポーネントであり、多くの場合、OCSLogger のコンポーネントと同じ名前を持っています。 OCSLogger に精通していないプロバイダーは、集中ログ サービスがログを収集できるサーバー役割固有のコンポーネントです。 集中ログ サービスの場合、CLSAgent は、プロバイダー構成で定義したコンポーネントのトレースを行う集中ログ サービスのアーキテクチャ部分です。
    
- **ログ レベル** OCSLogger には、収集されたデータの詳細レベルの数を選択するオプションが用意されています。 この機能は、集中ログ サービスとシナリオの不可欠な部分であり **、Type** パラメーターによって定義されます。 次の中から選択できます。
    
  - **All** 致命的、エラー、警告、詳細、デバッグの種類のトレース メッセージを、定義されたプロバイダーのログに収集します。
    
  - **致命的** "Fatal" として定義されたトレース メッセージのみを収集します。
    
  - **エラー** "Error" または "Fatal" として定義されたトレース メッセージのみを収集します。
    
  - **警告** "Warning"、"Error"、"Fatal" の種類のトレース メッセージのみを収集します。
    
  - **Info** 定義されたプロバイダーの情報メッセージに加えて、致命的なメッセージ、エラー メッセージ、および警告メッセージを示すトレース メッセージのみを収集します。
    
  - **Verbose** 定義されたプロバイダーの致命的、エラー、警告、詳細型のすべてのトレース メッセージを収集します。
    
  - **デバッグ** は、基本的には 'All' と同等です。定義されたプロバイダーの型 Fatal、Error、Warning、Info、Verbose、Debug のトレースを収集します。
    
- **フラグ** OCSLogger には、トレース ファイルから取得できる情報の種類を定義した各プロバイダーのフラグを選択するオプションが用意されています。 プロバイダーに基づいて、次のフラグを選択できます。
    
  - **TF_Connection** 接続関連のログ エントリを提供します。 これらのログには、特定のコンポーネントとの間で確立された接続に関する情報が含まれます。 これには、ネットワーク レベルの重要な情報 (つまり、接続の概念のないコンポーネント) も含まれる場合があります。
    
  - **TF_Security** セキュリティに関連するイベント/ログ エントリを提供します。 たとえば、SipStack の場合、これらはドメイン検証エラー、クライアント認証/承認エラーなどのセキュリティ イベントです。
    
  - **TF_Diag** コンポーネントの診断またはトラブルシューティングに使用できる診断イベントを提供します。 たとえば、SipStack の場合、これらは証明書の障害、または DNS の警告/エラーです。
    
  - **TF_Protocol** SIP メッセージや複合コミュニティ コーデック パック メッセージなどのプロトコル メッセージを提供します。
    
  - **TF_Component** プロバイダーの一部として指定されたコンポーネントのログを有効にします。
    
  - **All** プロバイダーで使用可能なすべてのフラグを設定します。
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>既存の集中ログ サービス シナリオ プロバイダーに関する情報を確認するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. 既存のプロバイダーの構成をレビューするには、次を入力します。
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    たとえば、グローバル会議アテンダントに関する情報をレビューするには、次のように入力します。
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    このコマンドは、関連するフラグ、設定、およびコンポーネントと共にプロバイダーの一覧を表示します。 表示される情報 Windows PowerShellが足りない場合や、既定のリスト形式でリストが長すぎる場合は、別の出力方法を定義して追加情報を表示できます。 これを行うには、次のように入力します。
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    このコマンドの出力では、各プロバイダーを行分割形式で表示します。プロバイダー名、ログの種類、ログ レベル、フラグ、GUID、および役割が行ごとに表示されます。 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>新しい集中ログ サービス シナリオ プロバイダーを定義するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. シナリオ プロバイダーは、トレースするコンポーネント、使用するフラグ、および収集する詳細レベルで構成されます。これは実行するには次のように入力します。
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    たとえば、Lyss プロバイダーから収集する内容および詳細レベルを定義するトレース プロバイダー定義は、次のようになります。
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

-Level は、致命的、エラー、警告、および情報メッセージを収集します。 使用されるフラグは、Lyss プロバイダー用に定義されたフラグのすべてであり、TF_Connection、TF_Diag、TF_Protocol が含まれます。変数 $LyssProvider を定義した後 **、New-CsClsScenario** コマンドレットと一緒に使用して、Lyss プロバイダーからトレースを収集できます。 このプロバイダーの作成と新しいシナリオへの割り当てを完了するには、次のように入力します。

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

$LyssProvider は、**New-CsClsProvider** で作成された定義済みのシナリオを含む変数です。
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>既存の集中ログ サービス シナリオ プロバイダーを変更するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. 既存のプロバイダーの構成を更新または変更するには、次のように入力します。
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    次のように入力することで、プロバイダーを割り当てるシナリオを更新します。
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

コマンドを実行すると、最終的にシナリオ site:Redmond/RedmondLyssInfo のフラグと割り当てられるプロバイダーのレベルが更新されます。 Get-CsClsScenario を使用して、新しいシナリオを表示できます。 詳細については、「[Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps)」を参照してください。
> [!CAUTION]
> **New-ClsCsProvider** は、フラグが有効かどうかを確認しません。 フラグのスペル (TF_DIAG や TF_CONNECTION など) が正しいことを確認してください。 フラグのスペルが正しくない場合、プロバイダーは期待されるログ情報を返すことができません。
  
このシナリオに対してプロバイダーを追加するには、次のように入力します。

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Add ディレクティブで定義される各プロバイダーは、**New-CsClsProvider** プロセスで既に定義されています。
### <a name="to-remove-a-scenario-provider"></a>シナリオ プロバイダーを削除するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. 用意されているコマンドレットを使用して、既存のプロバイダーの更新と新しいプロバイダーの作成を実行できます。 プロバイダーを削除するには、**Set-CsClsScenario** に対して Provider パラメーター用の Replace ディレクティブを使用する必要があります。 プロバイダーを完全に削除する唯一の方法は、Update ディレクティブを使用して、削除するプロバイダーを、再定義した同じ名前のプロバイダーに置き換えることです。 たとえば、プロバイダー LyssProvider は、ログの種類として WPP、レベルとして Debug、およびフラグとして TF_CONNECTION と TF_DIAG が定義されています。 フラグを "All" に変更する必要があります。 このプロバイダーを変更するには、次のように入力します。
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. シナリオとそれに関連付けられているプロバイダーを完全に削除するには、次のように入力します。
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    次に例を示します。
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > **Remove-CsClsScenario** コマンドレットは、確認のプロンプトを表示しません。 シナリオは、それに関連付けられているプロバイダーと共に削除されます。 シナリオを初めて作成したときに使用したコマンドを再実行することで、シナリオを再作成できます。 削除したシナリオまたはプロバイダーを回復するための手順はありません。
  
**Remove-CsClsScenario** コマンドレットを使用してシナリオを削除すると、シナリオはスコープから完全に削除されます。 作成したシナリオとシナリオの一部であったプロバイダーを使用するには、新しいプロバイダーを作成し、それらを新しいシナリオに割り当てます。
## <a name="see-also"></a>関連項目

[Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps)