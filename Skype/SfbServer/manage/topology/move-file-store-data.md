---
title: ファイル ストア データを Skype for Business Server の新しいファイル ストアに移動する
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
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: Skype for Business Server 展開のファイル ストアとして現在機能しているファイル サーバーを削除する必要がある場合、または現在のファイル ストアを使用できない他の変更を行う必要がある場合は、最初に新しい共有を作成する必要があります。 次に、次の手順を実行する必要があります。
ms.openlocfilehash: dbe9d239680d592a4d309d97577c6a6bad702239
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103173"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>ファイル ストア データを Skype for Business Server の新しいファイル ストアに移動する

Skype for Business Server 展開のファイル ストアとして現在機能しているファイル サーバーを削除する必要がある場合、または現在のファイル ストアを使用できない他の変更を行う必要がある場合は、最初に新しい共有を作成する必要があります。 次に、次の手順を実行する必要があります。

1. 削除する予定のファイル ストアを使用する Skype for Business Server サービスをシャットダウンします。

2. トポロジ ビルダーでファイル ストアを定義し、変更を発行して、新しいファイル ストアを展開で使用できます。

3. データを新しいファイル ストアに移動します。

4. サーバーまたはサービスを再起動します。

5. 必要に応じて、古いファイル共有とファイル フォルダーを削除します。

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>ファイル ストアのデータを新しいファイル ストアに移動するには

1. Skype for Business Server 管理ツールがインストールされている RTCUniversersalServerAdmins または CsServerAdministrator グループのメンバーとしてコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。

3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。

4. 削除する予定のファイル ストアを使用するディレクター プール、ディレクター、Standard Edition サーバー、およびフロントエンド プールごとに、サーバーまたはプールを選択し、[アクション]をクリックし、[すべてのサービスの停止] をクリックします。

5. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

6. トポロジ ビルダーの開始: [スタート] を **クリックし**、[すべてのプログラム] をクリックし **、[Skype for Business Server]** をクリックし、[Skype for Business Server トポロジ ビルダー]**をクリックします**。

7. ファイル ストアを使用するサーバーまたはプールを選択し、次の操作を行います。

   a. サーバーまたはプールを右クリックし、[プロパティの編集] **をクリックします**。

   b. [ **プロパティの編集]** の [ **関連付け]** の [ファイル ストア] **で**、[新規] を **クリックします**。

   c. [ **新しいファイル ストアの定義**] の [ファイル サーバー **FQDN]** で、ファイル サーバーの完全修飾ドメイン名 (FQDN) を入力します。 [ **ファイル共有] で**、新しいファイル共有のフォルダー名を入力し **、[OK] をクリックします**。

     > [!IMPORTANT]
     > この手順では、トポロジ ビルダーで使用する新しいファイル ストアを定義します。 サーバーごとにではなく、1 回だけ定義します。 トポロジを公開する前に、定義されたファイル共有を定義されたファイル サーバーに作成する必要があります。 詳細については、「[フロント エンドのファイル ストアの定義](/previous-versions/office/communications/gg133895(v=ocs.14))」を参照してください。

8. ファイル ストアを使用するサーバーまたはプールごとに、次の操作を行います。

   a. サーバーまたはプールを右クリックし、[プロパティの編集] **をクリックします**。

   b. [ **プロパティの編集]** の [ **関連付** け] の [ファイル ストア **] で**、新しいファイル共有を選択し **、[OK] をクリックします**。

9. トポロジを発行し、レプリケーションの状態を確認し、必要に応じて Skype for Business Server 展開ウィザードを実行します。 詳細については、「[Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14))」を参照してください。

10. コマンド プロンプトを開始する: [スタート] **をクリックし**、[ **実行**] をクリックし、「コマンド プロンプト」と入力cmd.exe。

11. コマンドラインで、次のように入力します。

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > /S スイッチは、ファイル、ディレクトリ、サブディレクトリをコピーします。 /XF スイッチは、Meeting.Active という名前のファイルをスキップします。 /MT スイッチを備えた現在のバージョンの robocopy.exe は、複数のスレッドを使用してコピーの速度を大幅に高めています。 /LOG スイッチの場合は、ディレクトリ パスとログ ファイル名をディレクトリ パスの形式でC:\Logfiles\log.txt。 このスイッチは、指定された場所に操作のログ ファイルを作成します。

12. データ コピーが完了したら、Lync Server コントロール パネルで [トポロジ] をクリックし、[状態] を **クリックします**。

13. サービスを停止したサーバーまたはプールごとに、サーバーまたはプールを選択し、[アクション]をクリックし、[すべてのサービスの開始 **] をクリックします**。

14. 古いファイル ストアをトポロジから削除し、トポロジを公開します。 詳細については、「[Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))」を参照してください。

15. (省略可能) 削除したファイル ストアを含むコンピューターに、ローカルの Administrators グループまたは Domain Admins グループのメンバーとしてログオンし、古いファイル共有とディレクトリを削除します。

## <a name="see-also"></a>関連項目

[サーバーの異なるファイル ストアへの再割り当て](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))

[ファイル ストアを削除する](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))