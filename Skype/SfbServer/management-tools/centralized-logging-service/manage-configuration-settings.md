---
title: Skype for Business Server 2015 の集中ログ サービスの構成設定の管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: '概要: Skype for Business Server 2015 の中央集中ログサービスの構成設定を取得、更新、作成する方法について説明します。'
ms.openlocfilehash: 20f62a5568bef6f11eab35e13fa4e4f7adf8102e
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991462"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の集中ログ サービスの構成設定の管理

**概要:** Skype for Business Server 2015 の中央集中ログサービスの構成設定を取得、更新、作成する方法について説明します。

一元化されたログサービスは、一元管理サービスコントローラー (CLSController) によって作成および使用される設定とパラメーターによって制御および構成され、個々のコンピューターの集中ログサービスエージェントにコマンドを送信します (CLSAgent)。 このエージェントは送信されたコマンドを処理し、(Start コマンドの場合は) シナリオ、プロバイダー、トレース期間、フラグの構成を使用して、提供された構成情報に従うトレース ログの収集を開始します。

> [!IMPORTANT]
>  一元管理のログサービス用に一覧表示されているすべての Windows PowerShell コマンドレットは、Skype for Business Server 2015 オンプレミスの展開で使用することを目的としていません。 機能しているように見えても、次のコマンドレットは、Skype for Business Server 2015 オンプレミスの展開で機能するように設計されていません。

-  **Csclsregion コマンドレット:** [Get-csclsregion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-csclsregion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)CsClsRegion、および削除された[csclsregion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。
-  **Csclssearchterm コマンドレット:** [取得-csclssearchterm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps)と[Set-csclssearchterm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。
-  **CsClsSecurityGroup コマンドレット:** [CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)、および[CsClsSecurityGroup を削除](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)します。

これらのコマンドレットで定義された設定により、悪影響を及ぼす可能性はありませんが、Microsoft Office 365 で使用するように設計されていますが、オンプレミスの展開で予期しない結果が返されることはありません。 これは、内部設置型展開ではこれらのコマンドレットが役に立たないという意味ではありませんが、その用途はより高度なトピックであるため、このドキュメントでは扱われません。

一元ログサービスは、1台のコンピューターまたはコンピューターのプールを含むスコープ (展開のコンピューターとプールのコレクションを含むサイトのレドモンドなどの定義されたサイト)、またはグローバルスコープで実行できます (つまり、配置内のコンピューターとプールのコレクションが含まれています)。[展開に含まれるすべてのコンピューターとプール] を選びます。

Skype for Business Server 管理シェルを使用して一元的なログサービスのスコープを構成するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、または、次の2つのグループのいずれかが含まれます。 このコマンドレットが割り当てられているすべての RBAC ロールの一覧 (自分自身で作成したカスタム RBAC ロールを含む) を返すには、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

次に例を示します。

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Windows PowerShell または CLSController で実行できるコマンドラインコマンドには、基本的な違いがあります。 Windows PowerShell には、シナリオを構成して定義するための豊富な方法が用意されています。また、トラブルシューティングシナリオには、わかりやすい方法でこれらのシナリオを再利用することもできます。 CLSController には、コマンドを発行して結果を取得するための高速で効率的な方法が用意されていますが、CLSController 用のコマンドセットは、コマンドラインから利用できる有限コマンドによって制限されます。 Windows PowerShell コマンドレットとは異なり、CLSController では、新しいシナリオを定義することはできません。サイトまたはグローバルレベルでスコープを管理することも、動的に構成できない有限コマンドセットに関するその他多くの制限事項もあります。 CLSController は、高速実行の手段を提供しますが、Windows PowerShell は、CLSController で可能な範囲を超えて一元的なログサービス機能を拡張するための手段を提供します。

1つのコンピューターのスコープは、 [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)の実行時に定義することができます。この場合は、[コンピューター []](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)パラメーターを使用して、 [[csclslogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)]、[Sync-csclslogging []、[](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)[同期-](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) csclslogging] の[各コマンドを](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)実行します。 -Computers パラメーターは、ターゲットコンピューターの完全修飾ドメイン名 (Fqdn) のコンマ区切りリストを受け取ります。

> [!TIP]
> また、プールと、ログコマンドを実行するプールのコンマ区切りリストを定義することもできます。

サイトとグローバルスコープ**は、****新しい****集中化さ**れたログサービスコマンドレットで定義されます。 以下の例は、サイト スコープとグローバル スコープを設定する方法を示しています。

> [!IMPORTANT]
> 表示されるコマンドには、他のセクションで説明するパラメーターと概念が含まれている場合があります。 この例のコマンドは、スコープを定義するために **-Identity**パラメーターを使うことを示すことを目的としています。その他のパラメーターは完全に含まれており、スコープを指定するために使用されます。 **Set-csclsconfiguration**コマンドレットの詳細については、「操作のドキュメントでの[Set-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) 」をご覧ください。

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>現在の集中化ログサービス構成を取得するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```PowerShell
   Get-CsClsConfiguration
   ```

新規の構成を作成するか、既存の構成を更新するには、**新しい-csclsconfiguration**コマンドレットと**Set-csclsconfiguration**コマンドレットを使用します。" **CsClsConfiguration の設定**を実行すると、次のスクリーンショットのような情報が表示されます。ここでは、現在は既定のグローバル構成があり、サイト構成は定義されていません。

![Get-CsClsConfiguration からのサンプル出力](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>コンピューターのローカルストアから現在の集中化されたログサービス構成を取得するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

最初の例の " **Get-CsClsConfiguration**でパラメーターが指定されていない" という最初の例を使用すると、コマンドはデータの中央管理ストアを参照します。 パラメーター-LocalStore を指定した場合、コマンドは中央管理ストアではなく、コンピューターの LocalStore を参照します。
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>現在定義されているシナリオの一覧を取得するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    たとえば、グローバル スコープで定義されているシナリオを取得するには、次のように入力します。

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

コマンドレットの**取得の構成**では、常に、特定のスコープ構成の一部であるシナリオが表示されます。 ほとんどの場合、シナリオがすべて表示されるのではなく、一部が切り捨てられます。 ここで使用するコマンドは、すべてのシナリオおよび使用されているプロバイダー、設定、およびフラグに関する一部の情報を一覧表示します。
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell を使用して一元的なログサービスのグローバルスコープを更新するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   次に例を示します。

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、展開内の各コンピューターおよびプールの CLSAgent に指示します。すべてのサイトのコンピューターとプールがこのコマンドの対象となり、コンピューターとプールの構成済みのトレース ログのロールオーバーの値が 40 MB に設定されます。
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell を使用して一元的なログサービスのサイト範囲を更新するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   次に例を示します。

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> この例に示すように、ログ ファイルの既定の場所は %TEMP%\Tracing です。ただし、これは実際にはファイルを書き込む CLSAgent であり、CSLAgent はネットワーク サービスとして実行されるため、%TEMP% 変数は %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。

このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、Redmond サイト内の各コンピューターおよびプールの CLSAgent に指示します。他のサイトのコンピューターとプールはこのコマンドの対象ではなく、現在構成されているトレース ログのロールオーバーの値 (既定値の 20 MB またはログ記録セッションの開始時に定義された値) が引き続き使用されます。
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>新しい一元ログサービス構成を作成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration を使用すると、オプションの多数の構成設定にアクセスできます。 構成オプションの詳細については、「 [CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) 」および「[一元ログサービスの構成設定につい](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)て」を参照してください。

たとえば、キャッシュ ファイル用のネットワーク フォルダー、ログ ファイルのロールオーバー時間、およびログ ファイルのロールオーバー サイズを定義する新しい構成を作成するには、次のように入力します。

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

新しい構成の作成を慎重に計画し、一元管理サービスの新しいプロパティを定義する方法を検討してください。 変更は慎重に行い、問題のシナリオのログを適切に記録する機能に及ぼす影響について理解しておいてください。 ログの管理機能を強化する、つまり発生した問題を解決するためのサイズおよびロールオーバー時間を定義できるように構成を変更する必要があります。
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>既存の一元ログサービス構成を削除するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. コマンド ライン プロンプトで次のように入力します。

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

たとえば、ログファイルのロールオーバー時間を増やすために作成した一元ログサービスの構成を削除するには、ロールオーバーログファイルのサイズを大きくして、次のようにログファイルキャッシュの場所をネットワーク共有に設定します。

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> これは、「新しい一元ログサービス構成を作成する」の手順で作成した新しい構成です。

サイト レベルの構成の削除を選択すると、そのサイトではグローバル設定が使用されます。
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 での集中ログ サービス プロバイダーの構成](configure-providers.md)

[Skype for Business Server 2015 での集中ログ サービスのシナリオの構成](configure-scenarios.md)

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[CsClsConfiguration の削除](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
