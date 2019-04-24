---
title: Skype for Business Server 2015 の集中ログ サービスの構成設定の管理
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 概要では、取得、更新、およびビジネス サーバー 2015 の Skype で集中ログ サービスの構成設定を作成する方法について説明します。
ms.openlocfilehash: 1aab363f88b7639e2eb61f9101864bac20cc0aa0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217515"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の集中ログ サービスの構成設定の管理

**の概要:** 取得、更新、およびビジネス サーバー 2015 の Skype で集中ログ サービスの構成設定を作成する方法について説明します。

集中ログ サービスを制御し、設定と作成され、個々 のコンピューターのログ サービス エージェントを集中型の (コマンドを送信するため、一元的なログ記録サービス コント ローラー (CLSController) 使用されているパラメーターによって構成されています。CLSAgent)。 このエージェントは送信されたコマンドを処理し、(Start コマンドの場合は) シナリオ、プロバイダー、トレース期間、フラグの構成を使用して、提供された構成情報に従うトレース ログの収集を開始します。

> [!IMPORTANT]
>  集中ログ サービスの一覧にないすべての Windows PowerShell コマンドレットは、使用する Skype でビジネス サーバー 2015 設置型展開では。 作業に見えるかもしれませんが、次のコマンドレットがビジネス サーバー 2015 設置型展開では、Skype で機能するために設計されていません。

-  **CsClsRegion コマンドレット:**[Get CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) [セット CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [CsClsRegion では新しい](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)、し、[削除 CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)します。
-  **CsClsSearchTerm コマンドレット:**[Get CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) [セット CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **CsClsSecurityGroup コマンドレット:**[Get CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)[セット CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [CsClsSecurityGroup では新しい](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)、し、[削除 CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)します。

これらのコマンドレットで定義された設定されないを低下させるか、任意の有害な動作が発生するが、Microsoft Office 365 で使用するために設計されていますが、設置型展開で期待どおりの結果には意味がありません。 これは、内部設置型展開ではこれらのコマンドレットが役に立たないという意味ではありませんが、その用途はより高度なトピックであるため、このドキュメントでは扱われません。

1 台のコンピューターまたはコンピューターのプールを含むスコープ、サイト スコープ (つまり、定義したサイトのコンピューターと、展開内のプールのコレクションを含む Redmond サイトなど)、またはグローバル スコープ (つまり、集中ログ サービスを実行することができます。、すべてのコンピューターと、展開内のプール)。

ビジネス サーバー管理シェルには、Skype を使用して、ログ サービスの一元的なスコープを構成するのには、CsAdministrator または CsServerAdministrator の役割に基づくアクセス制御 (RBAC) セキュリティ グループ、またはカスタムの RBAC の役割のいずれかのメンバーが必要ですこれら 2 つのグループのいずれかが含まれています。 (自分で作成したカスタムの RBAC の役割を含む) には、このコマンドレットが割り当てられているすべての RBAC の役割の一覧を返すするには、ビジネスのサーバー管理シェルまたは Windows PowerShell プロンプトに、Skype から次のコマンドを実行します。

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

次に例を示します。

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Windows PowerShell または CLSController で実行できるコマンド ライン コマンドの基本的な違いがあります。 Windows PowerShell を構成し、シナリオを定義して、トラブルシューティングのシナリオでは、意味のある方法でこれらのシナリオを再利用するのには、豊富なメソッドを提供します。 CLSController は、高速および効率のよいコマンドを発行し、結果を得るまで、CLSController は、有限で制限を設定するコマンド コマンドの中に、コマンドラインから使用可能ながあります。 Windows PowerShell コマンドレットとは異なり、CLSController は新しいシナリオを定義は可能で、サイトまたはグローバル レベル、および動的に構成することはできませんが、有限のコマンド セットの他の多くの制限の範囲を管理できません。 CLSController には、高速に実行の手段が用意されています、Windows PowerShell は CLSController で使用可能な対象外ログ サービスの集中管理機能を拡張するための手段を提供します。

[検索 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)、[ショー CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、[開始 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)、 [Stop CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)、[同期 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) [更新プログラム CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)の実行中に 1 台のコンピューターのスコープを定義することができます。コマンドを使用してコンピューターのパラメーターをします。 コンピューターのパラメーターは、ターゲット コンピューターの完全修飾ドメイン名 (Fqdn) のコンマ区切りのリストを受け入れます。

> [!TIP]
> 定義することも・ プールとコマンドのログを実行するプールのコンマ区切りのリストです。

**新規**、**セットを**および**削除の**一元的なログ記録サービスのコマンドレットでは、サイトおよびグローバル スコープが定義されています。 以下の例は、サイト スコープとグローバル スコープを設定する方法を示しています。

> [!IMPORTANT]
> 表示されるコマンドには、パラメーターとその他のセクションで説明する概念が含まれます。 コマンドの例の使用法を紹介するものでは、 **-の Id**のスコープを定義するパラメーターとその他のパラメーターは、完全を期すのため、スコープを指定するのには含まれています。 **セット CsClsConfiguration**コマンドレットの詳細については、操作マニュアルの[セットの CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)を参照してください。

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>現在のログ サービスの一元的な構成を取得するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```
   Get-CsClsConfiguration
   ```

新しい構成を作成または既存の構成を更新するのには、**新規 CsClsConfiguration**と**セット CsClsConfiguration**コマンドレットを使用します。**Get CsClsConfiguration**を実行すると、次のスクリーン ショット、展開されているデフォルトのグローバル設定ですが定義されているサイト構成はありませんのような情報が表示されます。

![Get-CsClsConfiguration からのサンプル出力](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>コンピューターのローカル ストアから現在のログ サービスの一元的な構成を取得するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```
   Get-CsClsConfiguration -LocalStore
   ```

使用する場合最初の例では、 **Get CsClsConfiguration**がすべてのパラメーター、コマンドの参照先を指定しない、中央管理ストアのデータです。 パラメーターを指定する場合、-LocalStore、コマンドは、中央管理ストアではなくコンピューターの LocalStore を参照します。
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>現在定義されているシナリオの一覧を取得するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    たとえば、グローバル スコープで定義されているシナリオを取得するには、次のように入力します。

   ```
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

**Get CsClsConfiguration**コマンドレットは、常に特定のスコープの構成の一部になっているシナリオを表示します。 ほとんどの場合、シナリオがすべて表示されるのではなく、一部が切り捨てられます。 ここで使用するコマンドは、すべてのシナリオおよび使用されているプロバイダー、設定、およびフラグに関する一部の情報を一覧表示します。
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell を使用して集中ログ サービスのグローバル スコープを更新するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   次に例を示します。

   ```
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、展開内の各コンピューターおよびプールの CLSAgent に指示します。すべてのサイトのコンピューターとプールがこのコマンドの対象となり、コンピューターとプールの構成済みのトレース ログのロールオーバーの値が 40 MB に設定されます。
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell を使用して集中ログ サービスのサイトの範囲を更新するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   次に例を示します。

   ```
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> この例に示すように、ログ ファイルの既定の場所は %TEMP%\Tracing です。ただし、これは実際にはファイルを書き込む CLSAgent であり、CSLAgent はネットワーク サービスとして実行されるため、%TEMP% 変数は %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。

このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、Redmond サイト内の各コンピューターおよびプールの CLSAgent に指示します。他のサイトのコンピューターとプールはこのコマンドの対象ではなく、現在構成されているトレース ログのロールオーバーの値 (既定値の 20 MB またはログ記録セッションの開始時に定義された値) が引き続き使用されます。
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>新しいログ サービスの一元的な構成を作成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration を使用すると、オプションの多数の構成設定にアクセスできます。 詳細構成オプションについては、 [Get CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)と[理解する一元的なログ記録サービス構成の設定](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)を参照してください。

たとえば、キャッシュ ファイル用のネットワーク フォルダー、ログ ファイルのロールオーバー時間、およびログ ファイルのロールオーバー サイズを定義する新しい構成を作成するには、次のように入力します。

  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

新しい構成および集中ログ サービスの新しいプロパティを定義する方法の作成を慎重に計画する必要があります。 変更は慎重に行い、問題のシナリオのログを適切に記録する機能に及ぼす影響について理解しておいてください。 ログの管理機能を強化する、つまり発生した問題を解決するためのサイズおよびロールオーバー時間を定義できるように構成を変更する必要があります。
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>既存のログ サービスの一元的な構成を削除するのには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

などのログ ファイルのロール オーバーの時間を増加するために作成するログ サービスの一元的な構成を削除するには、ロール オーバーのログ ファイル サイズを増やすし、ネットワーク共有にログ ファイルのキャッシュの場所を次のように設定。

  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> これは、新しい構成を作成する新しい集中ログ サービス構成します」の手順で作成されました。

サイト レベルの構成の削除を選択すると、そのサイトではグローバル設定が使用されます。
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 での集中ログ サービス プロバイダーの構成](configure-providers.md)

[Skype for Business Server 2015 での集中ログ サービスのシナリオの構成](configure-scenarios.md)

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[削除 CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
