---
title: 管理ツールのインストールおよび起動
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: このトピックでは、Skype for Business を展開して管理するために必要な管理ツールをインストールして開く方法について説明します。
ms.openlocfilehash: c720aba3998df8742406f4c9954f523b20e9af5f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816556"
---
# <a name="install-and-open-administrative-tools"></a>管理ツールのインストールおよび起動

このトピックでは、Skype for Business Server を展開して管理するために必要な管理ツールをインストールする方法について説明します。 管理ツールは、Skype for Business Server が実行されている各サーバーに既定でインストールされます。 さらに、専用の管理コンソールなど、他のコンピューターにも管理ツールをインストールできます。 作成している Skype for Business Server 展開と同じドメインまたはフォレストにあるコンピューターに管理ツールをインストールして、Active Directory ドメインサービスの準備手順が完了していることを確認することを強くお勧めします。これにより、後でそのコンピューターの管理ツールを使用してトポロジを公開できます。 また、Skype for Business Server 管理ツールをインストールまたは使用する前に、必要な要件を確認してください。 [Skype For Business server 2019](../../SfBServer2019/plan/system-requirements.md)または[Skype for business server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)の要件に関するドキュメントを参照してください。
 
> [!Important]
> 組織でインターネットインフォメーションサービス (IIS)、およびシステムドライブ以外のドライブ上のすべての Web サービスを検索する必要がある場合は、セットアップダイアログボックスで、Skype for Business Server ファイルのインストール場所のパスを変更することができます。 このパス (OCSCore など) にセットアップファイルをインストールすると、Skype for Business Server の他のファイルもこのドライブに展開されます。 

## <a name="to-install-the-administrative-tools"></a>管理ツールをインストールするには

1. 管理ツールをインストールするコンピューターにローカルの管理者 (最小要件) としてログオンします。 Windows で標準ユーザーとしてログオンしていて、ユーザーアカウント制御 (UAC) が有効になっている場合は、ローカルの管理者またはドメインの同等のユーザー名とパスワードを入力するように求められます。
2. 使用しているコンピューター上でインストールメディアを見つけて、[\ dcl amd64] をダブルクリックします。
3. Microsoft Visual C++ の配布可能な製品をインストールするかどうかを確認するメッセージが表示されたら、[**はい**] をクリックします。
4. [インストール先] ページで、[**OK**] をクリックします。 ファイルを別の場所にインストールする必要がある場合は、このパスを別の場所またはドライブに変更します。

    > [!Important]
    > 組織でインターネットインフォメーションサービス (IIS)、およびシステムドライブ以外のドライブ上のすべての Web サービスを検索する必要がある場合は、セットアップダイアログボックスで、Skype for Business Server ファイルのインストール場所のパスを変更することができます。 このパス (OCSCore など) にセットアップファイルをインストールすると、Skype for Business Server の他のファイルもこのドライブに展開されます。 

5. [エンドユーザーライセンス契約] ページで、ライセンス条項を確認し、[**同意**する] をクリックして、[ **OK**] をクリックします。 続行するには、この手順が必要です。
6. 展開ウィザードのページで、[**管理者ツールのインストール**] をクリックします。 
7. インストールが正常に完了したら、[**終了**] をクリックします。

次の手順を使用して、Skype for Business Server トポロジの展開、構成、トラブルシューティングを行うための管理ツールを開きます。

- [展開ウィザード](#deployment-wizard)
- [トポロジ ビルダー](#topology-builder) 
- [Skype for Business Server コントロール パネル](#skype-for-business-server-control-panel)
- [Skype for Business Server 管理シェル](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>展開ウィザード

コンポーネントファイルを追加または削除するために展開ウィザードをローカルで開始するには、次の手順に従います。

**Skype for Business Server 展開ウィザードを起動するには**

1. Skype for Business Server 展開ウィザードがドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンします。
2. [**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[ **skype for business server**] をクリックして、[ **skype for business server Deployment ウィザード**] をクリックします。


## <a name="topology-builder"></a>トポロジ ビルダー 

次の手順を使用して、[トポロジビルダー] を開いて、Skype for Business Server トポロジに展開するサーバーを定義します。

**Skype for Business Server トポロジビルダーを開いてトポロジを設計するには**

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    > [!NOTE]
    > トポロジは、ローカルユーザーグループのメンバーであるアカウントを使用して定義できますが、サーバーに Skype for Business Server をインストールするために必要なトポロジを読み取り、公開、有効にするには、ドメイン管理者グループのメンバーであるアカウントを使用する必要があります。e RTCUniversalServerAdmins グループ。また、アーカイブファイルストアで使用するファイル共有に対してフルコントロールのアクセス許可 (つまり読み取り、書き込み、変更) を持つことができます。これにより、必要な随意アクセス制御リストを構成できるようになります (Dacl)、または同等のユーザー権限を持つアカウント。
 
2. トポロジビルダーを開始します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for Business server**]、[ **skype for business server Topology Builder**] の順にクリックします。

## <a name="skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネル 

次のいずれかの手順を使用して、Skype for Business Server コントロールパネルを開き、環境内のサーバー、ユーザー、クライアント、およびデバイスの構成を管理します。

> [!NOTE]
> CsAdministrator ロールに割り当てられているユーザーアカウントを使用して、Skype for Business Server コントロールパネルで任意のタスクを実行することができます。 他の役割を使用して、Skype for Business Server コントロールパネルにログインして、実行する必要があるタスクに応じて、特定の管理タスクを実行することができます。 たとえば、CSArchivingAdministrator を使用して、Skype for Business Server コントロールパネルのアーカイブを管理することができます。 ロールの詳細については、「[ロールベースのアクセス制御の計画](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx)」を参照してください。 特定のタスクを実行するために使用できる役割の詳細については、そのタスクに関するドキュメントを参照してください。 

**組織のファイアウォール内の任意のコンピューターから Skype for Business Server コントロールパネルを開くには**

1. CsAdministrator の役割またはその他の役割に割り当てられているユーザーアカウントで、タスクを実行するための適切なユーザー権限と権限を持っている場合は、最小画面解像度 1024 x 768 を使用して、内部展開内の任意のコンピューターにログオンします。

    > [!IMPORTANT]
    > 管理のシンプルな uniform resource locator (URL) を構成している場合は、組織のファイアウォール内の任意のコンピューターで実行されているインターネットブラウザーから、Skype for Business Server コントロールパネルにアクセスできます。 管理のシンプルな URL の構成の詳細については、「単純な url[の計画](https://technet.microsoft.com/en-us/library/gg398287(v=ocs.15).aspx)」および「[単純な url の編集または構成](https://technet.microsoft.com/en-us/library/gg398063(v=ocs.15).aspx)」を参照してください。 

2. ブラウザーウィンドウを開き、組織に構成されている管理 URL を入力します。

**Skype for business server を実行しているコンピューターで、Skype for Business Server コントロールパネルを開くには**

1. CsAdministrator ロールのメンバーであるか、またはタスクの実行に適したユーザー権限と権限を持つユーザーアカウントから、Skype for Business Server をインストールしているコンピューターにログオンするか、少なくともSkype for Business Server 管理ツール。 設定を構成するには、コンピューターの画面解像度が 1024 x 768 以上である必要があります。
2. Skype for Business Server コントロールパネルを起動します。 [**スタート**]、[**すべてのプログラム**]、[**管理ツール**]、[ **skype for business server**] の順にポイントして、[ **skype for business server コントロールパネル**] をクリックします。

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェル 

次の手順を使用して、コマンドラインを使用して、環境内のサーバー、ユーザー、クライアント、デバイスを管理するための Skype for Business Server 管理シェルを開きます。

> [!NOTE]
> CsAdministrator ロールに割り当てられているユーザーアカウントを使用して、Skype for Business Server 管理シェルで任意のタスクを実行することができます。 他の役割を使用してログオンし、実行する必要があるタスクに応じて、特定の管理タスクを実行できます。 たとえば、CSArchivingAdministrator を使用して、アーカイブ管理に関連するコマンドレットを実行することができます。 ロールの詳細については、「[ロールベースのアクセス制御の計画](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx)」を参照してください。 特定のコマンドレットを実行するために使用できる役割の詳細については、コマンドレットのドキュメントを参照してください。<br/><br/>また、コマンドレットに応じて、RTCUniversalServerAdmins、RTCUniversalUserAdmins、または RTCUniversalReadOnlyAdmins グループのユーザーアカウントを使用して、特定のコマンドレットを実行することもできます。 

**Skype for Business Server 管理シェルを開くには**

Skype for Business Server 管理シェルではなく、Windows PowerShell ウィンドウを開いた場合、既定では、Skype for Business Server コマンドレットを実行することはできません。 Windows PowerShell 内から Skype for Business Server コマンドレットを実行するには、Windows PowerShell コマンドプロンプトで次のように入力します。

`Import-Module Lync`

Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**] をクリックします。次に、[skype **for business server**] をクリックし、[ **skype for business server 管理シェル**] をクリックします。
