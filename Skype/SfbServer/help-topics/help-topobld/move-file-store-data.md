---
title: Skype for Business Server 2015 の新しいファイルストアへのファイルストアデータの移動
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 現在、Skype for Business Server 2015 展開のファイルストアとして機能しているファイルサーバーを削除する必要がある場合、または現在のファイルストアを使用できないようにする他の変更を行う必要がある場合は、まず新しい共有を作成する必要があります。 その後、次の手順を実行する必要があります。
ms.openlocfilehash: c9bdc7ac572ecd8a71022e5a267454b795ef7cc6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215588"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の新しいファイルストアへのファイルストアデータの移動

現在、Skype for Business Server 2015 展開のファイルストアとして機能しているファイルサーバーを削除する必要がある場合、または現在のファイルストアを使用できないようにする他の変更を行う必要がある場合は、まず新しい共有を作成する必要があります。 その後、次の手順を実行する必要があります。

1. 削除する予定のファイルストアを使用する Skype for Business Server 2015 サービスをシャットダウンします。

2. トポロジビルダーでファイルストアを定義し、変更を公開して、新しいファイルストアを展開で使用できるようにします。

3. データを新しいファイルストアに移動します。

4. サーバーまたはサービスを再起動します。

5. 必要に応じて、古いファイル共有とファイルフォルダーを削除します。

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>ファイル ストアのデータを新しいファイル ストアに移動するには

1. Skype for Business Server 2015 の管理ツールがインストールされている RTCUniversersalServerAdmins または CsServerAdministrator グループのメンバーとしてコンピューターにログオンします。

2. ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。

4. 削除する予定のファイルストアを使用する各ディレクタープール、ディレクター、Standard Edition サーバー、フロントエンドプールについて、サーバーまたはプールを選択し、[ **アクション**] をクリックして、[ **すべてのサービスの停止**] をクリックします。

5. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

6. トポロジビルダーを起動します。 [ **スタート**]、[ **すべてのプログラム**]、[ **skype for business Server 2015**]、[ **Skype for business server 2015topology ビルダー**] の順にクリックします。

7. ファイルストアを使用するサーバーまたはプールを選択し、次の操作を行います。

8. サーバーまたはプールを右クリックし、[ **プロパティの編集**] をクリックします。

9. [ **プロパティの編集**] の [ **関連付け**] の [ **ファイルストア**] で、[ **新規**] をクリックします。

10. [ **新しいファイルストアの定義**] の [ **ファイルサーバーの fqdn**] で、ファイルサーバーの完全修飾ドメイン名 (fqdn) を入力します。 [ **ファイル共有**] の下で、新しいファイル共有のフォルダー名を入力し、[ **OK**] をクリックします。

     > [!IMPORTANT]
     > この手順では、トポロジビルダーで使用する新しいファイルストアを定義します。 これは、サーバーごとにではなく、1回だけ定義します。 トポロジを公開する前に、定義されたファイルサーバー上に定義済みのファイル共有を作成する必要があります。 詳細については、「[フロント エンドのファイル ストアの定義](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)」を参照してください。

11. ファイルストアを使用するサーバーまたはプールごとに、次の操作を行います。

12. サーバーまたはプールを右クリックし、[ **プロパティの編集**] をクリックします。

13. [ **プロパティの編集**] の [ **関連付け**] の [ **ファイルストア**] で、新しいファイル共有を選択して、[ **OK**] をクリックします。

14. トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Skype for Business Server 展開ウィザードを実行します。 詳細については、「[Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)」を参照してください。

15. コマンドプロンプトを起動します。 [ **スタート**] をクリックし、[ **実行**] をクリックして、cmd.exe を入力します。

16. コマンドラインで、次のように入力します。

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > /S スイッチは、ファイル、ディレクトリ、サブディレクトリにコピーします。 /XF スイッチは、Meeting という名前のすべてのファイルをスキップします。 /MT スイッチを備えた現在のバージョンの robocopy.exe は、複数のスレッドを使用してコピーの速度を大幅に高めています。 /LOG スイッチでは、ディレクトリパスとログファイル名を C:\Logfiles\log.txt の形式で使用します。 このスイッチは、指定した場所に操作のログファイルを作成します。

17. データのコピーが完了したら、Lync Server コントロールパネルで [ **トポロジ**] をクリックし、[ **状態**] をクリックします。

18. サービスを停止したサーバーまたはプールごとに、サーバーまたはプールを選択し、[ **アクション**] をクリックして、[ **すべてのサービスの開始**] をクリックします。

19. 古いファイル ストアをトポロジから削除し、トポロジを公開します。 詳細については、「[Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)」を参照してください。

20. (省略可能) 削除したファイル ストアを含むコンピューターに、ローカルの Administrators グループまたは Domain Admins グループのメンバーとしてログオンし、古いファイル共有とディレクトリを削除します。

## <a name="see-also"></a>関連項目

[サーバーの異なるファイル ストアへの再割り当て](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[ファイルストアを削除する](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
