---
title: 管理ツールのインストールおよび起動
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: このトピックでは、Skype for Business の展開と管理に必要な管理ツールをインストールして開く方法について説明します。
ms.openlocfilehash: d31fe784b62a5d709049dc5061e323034065df37
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835097"
---
# <a name="install-and-open-administrative-tools"></a>管理ツールのインストールおよび起動

このトピックでは、Skype for Business Server の展開と管理に必要な管理ツールをインストールする方法について説明します。 管理ツールは、Skype for Business Server を実行している各サーバーに既定でインストールされます。 また、専用の管理コンソールなど、他のコンピューター上に管理ツールをインストールすることもできます。 Active Directory ドメイン サービスの準備手順が既に完了し、後でそのコンピューターの管理ツールを使用してトポロジを公開するために、作成する Skype for Business Server 展開と同じドメインまたはフォレスト内にあるコンピューターに管理ツールをインストールすることを強く推奨します。 また、Skype for Business Server 管理ツールをインストールまたは使用する前に、必要な要件を確認してください。 Skype for Business [Server 2019 または Skype for Business Server 2015](../../SfBServer2019/plan/system-requirements.md) の要件に関するドキュメントを [参照](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)してください。
 
> [!Important]
> 組織でインターネット インフォメーション サービス (IIS) とすべての Web サービスをシステム ドライブ以外のドライブに配置する必要がある場合は、[セットアップ] ダイアログ ボックスで Skype for Business Server ファイルのインストール場所のパスを変更できます。 OCSCore.msi を含むこのパスにセットアップ ファイルをインストールすると、残りの Skype for Business Server ファイルもこのドライブに展開されます。 

## <a name="to-install-the-administrative-tools"></a>管理ツールをインストールするには

1. 管理ツールのインストール先のコンピューターにローカル管理者 (最小要件) としてログオンします。 Windows で標準ユーザーとしてログオンし、ユーザー アカウント制御 (UAC) が有効になっている場合は、ローカル管理者またはドメインと同等のユーザー名とパスワードの入力を求められます。
2. コンピューターにインストール メディアを配置し、\Setup\amd64\Setup.exe をダブルクリックします。
3. Microsoft Visual C++ を配布可能にインストールするように求めるメッセージが表示されたら、[はい] を **クリックします**。
4. [インストール場所] ページで **、[OK] をクリックします**。 ファイルを他の場所にインストールする必要がある場合は、このパスを他の場所またはドライブに変更します。

    > [!Important]
    > 組織でインターネット インフォメーション サービス (IIS) とすべての Web サービスをシステム ドライブ以外のドライブに配置する必要がある場合は、[セットアップ] ダイアログ ボックスで Skype for Business Server ファイルのインストール場所のパスを変更できます。 OCSCore.msi を含むこのパスにセットアップ ファイルをインストールすると、残りの Skype for Business Server ファイルもこのドライブに展開されます。 

5. [使用許諾契約書] ページでライセンス条項を確認し、[**同意する**] をクリックしてから [**OK**] をクリックします。 続行するにはこのステップが必要です。
6. [展開ウィザード] ページで、[管理者ツールの **インストール] をクリックします**。 
7. インストールが正常に完了したら、[**終了**] をクリックします。

次の手順を使用して、Skype for Business Server トポロジを展開、構成、またはトラブルシューティングするための管理ツールを開きます。

- [展開ウィザード](#deployment-wizard)
- [トポロジ ビルダー](#topology-builder) 
- [Skype for Business Server コントロール パネル](#skype-for-business-server-control-panel)
- [Skype for Business Server 管理シェル](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>展開ウィザード

次の手順を使用して、展開ウィザードをローカルで開始し、コンポーネント ファイルを追加または削除します。

**Skype for Business Server 展開ウィザードを開始するには**

1. Skype for Business Server 展開ウィザードがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
2. [ **スタート] ボタン**、[すべてのプログラム] **の順** にクリックし **、[Skype for Business Server]** をクリックして、[Skype for Business Server 展開ウィザード **] をクリックします**。


## <a name="topology-builder"></a>トポロジ ビルダー 

以下の手順を使用して、トポロジ ビルダーを開き、Skype for Business Server トポロジに展開するサーバーを定義します。

**Skype for Business Server トポロジ ビルダーを開き、トポロジを設計するには**

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    > [!NOTE]
    > ローカル Users グループのメンバーであるアカウントを使用してトポロジを定義できますが、Skype for Business Server をサーバーにインストールするために必要なトポロジの読み取り、公開、または有効化を行う場合は、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーであり、フル コントロールのアクセス許可 (つまり、、読み取り、書き込み、および変更) をアーカイブ ファイル ストアに使用して、トポロジ ビルダーが必要な随意アクセス制御リスト (DACL) または同等のユーザー権限を持つアカウントを構成できます。
 
2. トポロジ ビルダーを起動します **。[** スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server]** をクリックして、[Skype for Business Server トポロジ ビルダー]**をクリックします**。

## <a name="skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネル 

次のいずれかの手順を使用して、Skype for Business Server コントロール パネルを開き、環境内のサーバー、ユーザー、クライアント、およびデバイスの構成を管理します。

> [!NOTE]
> CsAdministrator の役割に割り当てられているユーザー アカウントを使用して、Skype for Business Server コントロール パネルで任意のタスクを実行できます。 他の役割を使用して Skype for Business Server コントロール パネルにログオンし、実行する必要があるタスクに応じて特定の管理タスクを実行できます。 たとえば、CSArchivingAdministrator を使用して、Skype for Business Server コントロール パネルでアーカイブを管理できます。 役割の詳細については、「役割ベースの [アクセス制御の計画」を参照してください](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx)。 特定のタスクを実行する場合に使用できる役割の詳細については、該当タスクのドキュメントを参照してください。 

**組織のファイアウォール内の任意のコンピューターから Skype for Business Server コントロール パネルを開く方法**

1. CsAdministrator の役割、またはタスクを実行するための適切なユーザー権限とアクセス許可を持つその他の役割に割り当てられているユーザー アカウントから、最小画面解像度 1024 x 768 の内部展開の任意のコンピューターにログオンします。

    > [!IMPORTANT]
    > 管理用の簡易 URL (Uniform Resource Locator) を構成している場合は、組織のファイアウォール内の任意のコンピューターで実行されているインターネット ブラウザーから Skype for Business Server コントロール パネルにアクセスできます。 管理簡易 URL の構成の詳細については、「簡易 URL の計画」および「簡易 URL[の編集または](https://technet.microsoft.com/library/gg398287(v=ocs.15).aspx)[構成」を参照してください](https://technet.microsoft.com/library/gg398063(v=ocs.15).aspx)。 

2. ブラウザー ウィンドウを開き、組織に対して構成されている管理 URL を入力します。

**Skype for Business Server を実行しているコンピューターで Skype for Business Server コントロール パネルを開く方法**

1. CsAdministrator の役割またはタスクを実行するための適切なユーザー権限とアクセス許可を持つその他の役割のメンバーであるユーザー アカウントから、Skype for Business Server をインストールしたコンピューター、または少なくとも Skype for Business Server 管理ツールにログオンします。 設定を構成するには、コンピューターの画面解像度が 1024 x 768 以上である必要があります。
2. Start Skype for Business Server Control Panel: Click **Start**, click **All Programs**, point to **Administrative Tools,** point **to Skype for Business Server,** and then click **Skype for Business Server Control Panel.**

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェル 

次の手順を使用して、Skype for Business Server 管理シェルを開き、コマンド ラインを使用して環境内のサーバー、ユーザー、クライアント、およびデバイスを管理します。

> [!NOTE]
> CsAdministrator の役割に割り当てられているユーザー アカウントを使用して、Skype for Business Server 管理シェル で任意のタスクを実行できます。 特定の管理タスクを実行するには、実行する必要があるタスクに応じて、他の役割を使用してログオンできます。 たとえば、CSArchivingAdministrator を使用することで、アーカイブ管理に管理するコマンドレットを実行できます。 役割の詳細については、「役割ベースの [アクセス制御の計画」を参照してください](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx)。 特定のコマンドレットを実行する場合に使用できる役割の詳細については、該当コマンドレットのドキュメントを参照してください。<br/><br/>コマンドレットに応じて、RTCUniversalServerAdmins、RTCUniversalUserAdmins、または RTCUniversalReadOnlyAdmins の各グループのユーザー アカウントを使用して、特定のコマンドレットを実行することもできます。 

**Skype for Business Server 管理シェルを開く方法**

Skype for Business Server 管理シェルWindows PowerShell新しいウィンドウを開く場合、既定では Skype for Business Server コマンドレットを実行できません。 Skype for Business Server コマンドレットを Windows PowerShellから実行するには、次のコマンド プロンプトで次Windows PowerShell入力します。

`Import-Module Lync`

Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
