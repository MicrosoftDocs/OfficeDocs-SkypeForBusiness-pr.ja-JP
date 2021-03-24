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
ms.openlocfilehash: 72966026e414b3b36cfc49ab61bf41f045e1f864
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098783"
---
# <a name="install-and-open-administrative-tools"></a>管理ツールのインストールおよび起動

このトピックでは、Skype for Business Server を展開および管理するために必要な管理ツールをインストールする方法について説明します。 管理ツールは、Skype for Business Server を実行している各サーバーに既定でインストールされます。 また、専用の管理コンソールなど、他のコンピューター上に管理ツールをインストールすることもできます。 作成する Skype for Business Server 展開と同じドメインまたはフォレスト内のコンピューターに管理ツールをインストールし、Active Directory ドメイン サービスの準備手順が既に完了し、後でそのコンピューターの管理ツールを使用してトポロジを公開することを強く推奨します。 また、Skype for Business Server 管理ツールをインストールまたは使用する前に、必要な要件を確認してください。 [「Skype for Business Server 2019」または「Skype for Business Server 2015」](../../SfBServer2019/plan/system-requirements.md)の要件に関するドキュメントを[参照してください](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。
 
> [!Important]
> 組織で、システム ドライブ以外のドライブでインターネット インフォメーション サービス (IIS) とすべての Web サービスを見つける必要がある場合は、[セットアップ] ダイアログ ボックスで Skype for Business Server ファイルのインストール場所パスを変更できます。 セットアップ ファイルをこのパス (OCSCore.msi を含む) にインストールすると、残りの Skype for Business Server ファイルもこのドライブに展開されます。 

## <a name="to-install-the-administrative-tools"></a>管理ツールをインストールするには

1. 管理ツールのインストール先のコンピューターにローカル管理者 (最小要件) としてログオンします。 Windows で標準ユーザーとしてログオンし、ユーザー アカウント制御 (UAC) が有効になっている場合は、ローカル管理者またはドメインと同等のユーザー名とパスワードの入力を求めるメッセージが表示されます。
2. コンピューターにインストール メディアを配置し、\Setup\amd64\Setup.exe をダブルクリックします。
3. 配布可能な Microsoft サーバーをインストールするように求Visual C++場合は、[はい] を **クリックします**。
4. [インストール場所] ページで **、[OK] をクリックします**。 ファイルを他の場所にインストールする必要がある場合は、このパスを他の場所またはドライブに変更します。

    > [!Important]
    > 組織で、システム ドライブ以外のドライブでインターネット インフォメーション サービス (IIS) とすべての Web サービスを見つける必要がある場合は、[セットアップ] ダイアログ ボックスで Skype for Business Server ファイルのインストール場所パスを変更できます。 セットアップ ファイルをこのパス (OCSCore.msi を含む) にインストールすると、残りの Skype for Business Server ファイルもこのドライブに展開されます。 

5. [使用許諾契約書] ページでライセンス条項を確認し、[**同意する**] をクリックしてから [**OK**] をクリックします。 続行するにはこのステップが必要です。
6. [展開ウィザード] ページで、[管理者ツールの **インストール] をクリックします**。 
7. インストールが正常に完了したら、[**終了**] をクリックします。

次の手順を使用して、Skype for Business Server トポロジを展開、構成、またはトラブルシューティングするための管理ツールを開きます。

- [展開ウィザード](#deployment-wizard)
- [トポロジ ビルダー](#topology-builder) 
- [Skype for Business Server コントロール パネル](#skype-for-business-server-control-panel)
- [Skype for Business Server 管理シェル](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>展開ウィザード

次の手順を使用して、展開ウィザードをローカルで開始して、コンポーネント ファイルを追加または削除します。

**Skype for Business Server 展開ウィザードを開始するには**

1. Skype for Business Server 展開ウィザードがドメイン管理者グループおよび RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンします。
2. [ **スタート] ボタン**、[ **すべてのプログラム] の** 順にクリックし **、[Skype for Business Server]** をクリックし **、[Skype for Business Server 展開ウィザード] をクリックします**。


## <a name="topology-builder"></a>トポロジ ビルダー 

次の手順を使用してトポロジ ビルダーを開き、Skype for Business Server トポロジに展開するサーバーを定義します。

**Skype for Business Server トポロジ ビルダーを開き、トポロジを設計するには**

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    > [!NOTE]
    > トポロジを定義するには、ローカル の Users グループのメンバーですが、サーバーに Skype for Business Server をインストールするために必要なトポロジの読み取り、公開、または有効化を行うアカウントを使用して、Domain Admins グループと RTCUniversalServerAdmins グループのメンバーであり、完全な制御アクセス許可を持つアカウントを使用する必要があります (つまり、、読み取り、書き込み、および変更) をアーカイブ ファイル ストアに使用するファイル共有で、トポロジ ビルダーが必要な任意アクセス制御リスト (DACL) または同等のユーザー権限を持つアカウントを構成できます。
 
2. トポロジ ビルダーの開始: [スタート] を **クリックし**、[すべてのプログラム] をクリックし **、[Skype for Business Server]** をクリックし、[Skype for Business Server トポロジ ビルダー]**をクリックします**。

## <a name="skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネル 

次のいずれかの手順を使用して、Skype for Business Server コントロール パネルを開いて、環境内のサーバー、ユーザー、クライアント、およびデバイスの構成を管理します。

> [!NOTE]
> CsAdministrator 役割に割り当てられているユーザー アカウントを使用して、Skype for Business Server コントロール パネルで任意のタスクを実行できます。 他の役割を使用して Skype for Business Server コントロール パネルにログオンし、実行する必要があるタスクに応じて、特定の管理タスクを実行できます。 たとえば、CSArchivingAdministrator を使用して、Skype for Business Server コントロール パネルでアーカイブを管理できます。 役割の詳細については、「役割ベースのアクセス [制御の計画」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)。 特定のタスクを実行する場合に使用できる役割の詳細については、該当タスクのドキュメントを参照してください。 

**組織のファイアウォール内の任意のコンピューターから Skype for Business Server コントロール パネルを開く方法**

1. CsAdministrator 役割またはタスクを実行するための適切なユーザー権限とアクセス許可を持つ他の役割に割り当てられているユーザー アカウントから、最小画面解像度が 1024 x 768 の内部展開の任意のコンピューターにログオンします。

    > [!IMPORTANT]
    > 管理簡易統一リソース ロケーター (URL) を構成している場合は、組織のファイアウォール内の任意のコンピューターで実行されているインターネット ブラウザーから Skype for Business Server コントロール パネルにアクセスできます。 管理簡易 URL の構成の詳細については、「簡易 URL の計画 [」](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls) および「簡易 URL の編集または構成」 [を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-edit-or-configure-simple-urls)。 

2. ブラウザー ウィンドウを開き、組織に対して構成されている管理 URL を入力します。

**Skype for Business Server を実行しているコンピューターで Skype for Business Server コントロール パネルを開く方法**

1. 実行するタスクの適切なユーザー権限とアクセス許可を持つ CsAdministrator 役割または他の役割のメンバーであるユーザー アカウントから、Skype for Business Server をインストールしたコンピューターにログオンするか、少なくとも Skype for Business Server 管理ツールにログオンします。 設定を構成するには、コンピューターの最小画面解像度が 1024 x 768 である必要があります。
2. Skype for Business Server コントロール パネルを起動する: [スタート] をクリックし、[すべてのプログラム] をクリックし、[管理ツール] をポイントし **、[Skype for Business Server]** をポイントし、[Skype for Business Server コントロール パネル]**をクリックします**。 

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェル 

次の手順を使用して、Skype for Business Server 管理シェルを開き、コマンド ラインを使用して環境内のサーバー、ユーザー、クライアント、デバイスを管理します。

> [!NOTE]
> CsAdministrator 役割に割り当てられているユーザー アカウントを使用して、Skype for Business Server 管理シェルで任意のタスクを実行できます。 特定の管理タスクを実行するには、実行する必要があるタスクに応じて、他の役割を使用してログオンできます。 たとえば、CSArchivingAdministrator を使用することで、アーカイブ管理に管理するコマンドレットを実行できます。 役割の詳細については、「役割ベースのアクセス [制御の計画」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)。 特定のコマンドレットを実行する場合に使用できる役割の詳細については、該当コマンドレットのドキュメントを参照してください。<br/><br/>コマンドレットに応じて、RTCUniversalServerAdmins、RTCUniversalUserAdmins、または RTCUniversalReadOnlyAdmins の各グループのユーザー アカウントを使用して、特定のコマンドレットを実行することもできます。 

**Skype for Business Server 管理シェルを開く方法**

Skype for Business Server 管理シェルWindows PowerShellウィンドウを開く場合、既定では Skype for Business Server コマンドレットを実行できません。 Skype for Business Server コマンドレットを Windows PowerShellから実行するには、次のコマンド プロンプトWindows PowerShell入力します。

`Import-Module Lync`

Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business Server]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。