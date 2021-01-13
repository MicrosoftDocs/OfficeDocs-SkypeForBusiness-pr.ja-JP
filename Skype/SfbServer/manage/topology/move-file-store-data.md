---
title: Skype for Business Server でファイル ストア データを新しいファイル ストアに移動する
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
description: Skype for Business Server 展開のファイル ストアとして現在機能しているファイル サーバーを削除する必要がある場合、または現在のファイル ストアを使用できなくなるその他の変更を行う必要がある場合は、最初に新しい共有を作成する必要があります。 その後、次の手順を実行する必要があります。
ms.openlocfilehash: 1ea1f6f038a5d589f9a2c3f480a5c9e589c324f3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816367"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Skype for Business Server でファイル ストア データを新しいファイル ストアに移動する

Skype for Business Server 展開のファイル ストアとして現在機能しているファイル サーバーを削除する必要がある場合、または現在のファイル ストアを使用できなくなるその他の変更を行う必要がある場合は、最初に新しい共有を作成する必要があります。 その後、次の手順を実行する必要があります。

1. 削除する予定のファイル ストアを使用する Skype for Business Server サービスをシャットダウンします。

2. トポロジ ビルダーでファイル ストアを定義し、変更を公開して、新しいファイル ストアを展開で使用できます。

3. データを新しいファイル ストアに移動します。

4. サーバーまたはサービスを再起動します。

5. 必要に応じて、古いファイル共有とファイル フォルダーを削除します。

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>ファイル ストアのデータを新しいファイル ストアに移動するには

1. Skype for Business Server 管理ツールがインストールされている RTCUniversersalServerAdmins または CsServerAdministrator グループのメンバーとしてコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。

3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。

4. 削除する予定のファイル ストアを使用するディレクター プール、ディレクター、Standard Edition サーバー、およびフロントエンド プールごとに、サーバーまたはプールを選択し、[操作] をクリックして、[すべてのサービスの停止] をクリック **します。**

5. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

6. トポロジ ビルダーを起動します **。[** スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server]** をクリックして、[Skype for Business Server トポロジ ビルダー]**をクリックします**。

7. ファイル ストアを使用するサーバーまたはプールを選択し、次の操作を行います。

   a.  サーバーまたはプールを右クリックし、[プロパティの編集] **をクリックします**。

   b. [**プロパティの編集] の**[関連 **付け] で、[****ファイル** ストア] の [新規] を **クリックします**。

   c. [ **新しいファイル ストア** の定義] の [ファイル サーバー **の FQDN]** で、ファイル サーバーの完全修飾ドメイン名 (FQDN) を入力します。 [ **ファイル共有] で**、新しいファイル共有のフォルダー名を入力し **、[OK]** をクリックします。

     > [!IMPORTANT]
     > この手順では、トポロジ ビルダーで使用する新しいファイル ストアを定義します。 サーバーごとに定義するのではなく、1 回だけ定義します。 トポロジを公開する前に、定義されたファイル共有を定義したファイル サーバー上に作成する必要があります。 詳細については、「[フロント エンドのファイル ストアの定義](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)」を参照してください。

8. ファイル ストアを使用するサーバーまたはプールごとに、次の操作を行います。

   a.  サーバーまたはプールを右クリックし、[プロパティの編集] **をクリックします**。

   b. [ **プロパティの編集] の** **[関連付** け] の [ファイル ストア] **で、新** しいファイル共有を選択し **、[OK]** をクリックします。

9. トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Skype for Business Server 展開ウィザードを実行します。 詳細については、「[Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)」を参照してください。

10. コマンド プロンプトを起動します。[スタート] **ボタンをクリックし**、[ファイル名を指定して **実行**] cmd.exe。

11. コマンドラインで、次のように入力します。

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > /S スイッチは、ファイル、ディレクトリ、サブディレクトリをコピーします。 /XF スイッチは、Meeting.Active という名前のファイルをスキップします。 /MT スイッチを備えた現在のバージョンの robocopy.exe は、複数のスレッドを使用してコピーの速度を大幅に高めています。 /LOG スイッチの場合は、ディレクトリ パスとログ ファイル名をディレクトリ パスの形式で使用C:\Logfiles\log.txt。 このスイッチは、指定された場所に操作のログ ファイルを作成します。

12. データ コピーが完了したら、Lync Server コントロール パネルで [トポロジ] をクリックし、[状態] を **クリックします**。

13. サービスを停止したサーバーまたはプールごとに、サーバーまたはプールを選択し、[操作]をクリックして、[すべてのサービスの開始 **] をクリックします**。

14. 古いファイル ストアをトポロジから削除し、トポロジを公開します。 詳細については、「[Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)」を参照してください。

15. (省略可能) 削除したファイル ストアを含むコンピューターに、ローカルの Administrators グループまたは Domain Admins グループのメンバーとしてログオンし、古いファイル共有とディレクトリを削除します。

## <a name="see-also"></a>関連項目

[サーバーの異なるファイル ストアへの再割り当て](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[ファイル ストアを削除する](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
