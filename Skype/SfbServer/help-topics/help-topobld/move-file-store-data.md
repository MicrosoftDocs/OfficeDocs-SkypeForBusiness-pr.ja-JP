---
title: Skype for Business Server 2015 での新しいファイル ストアへのファイル ストア データの移動
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: Skype for Business Server 2015 の展開のために現在ファイルストアとして機能しているファイルサーバーを削除する必要がある場合、または現在のファイルストアを使用できないその他の変更を行う必要がある場合は、最初に新しい共有を作成する必要があります。 その後、次の手順を実行する必要があります。
ms.openlocfilehash: c2d447734d05b03b54a27640be872d360658636d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285618"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>Move File Store Data to a New File Store in Skype for Business Server 2015

Skype for Business Server 2015 の展開のために現在ファイルストアとして機能しているファイルサーバーを削除する必要がある場合、または現在のファイルストアを使用できないその他の変更を行う必要がある場合は、最初に新しい共有を作成する必要があります。 その後、次の手順を実行する必要があります。

1. 削除する予定のファイルストアを使用している Skype for Business Server 2015 サービスをシャットダウンします。

2. トポロジビルダーでファイルストアを定義し、変更内容を公開して、新しいファイルストアを展開で利用できるようにします。

3. 新しいファイル ストアにデータを移行します。

4. サーバーまたはサービスを再起動します。

5. オプションで、古いファイル共有とファイル フォルダーを削除します。

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>ファイル ストアのデータを新しいファイル ストアに移動するには

1. 管理ツールがインストールされている RTCUniversersalServerAdmins または csserveradministrator 2015 グループのメンバーとしてコンピューターにログオンします。

2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。

4. 削除する予定のファイルストアを使用している各ディレクタープール、監督、Standard Edition サーバー、およびフロントエンドプールでは、サーバーまたはプールを選択し、[**操作**] をクリックして、[**すべてのサービスの停止**] をクリックします。

5. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

6. トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **skype for business Server 2015**]、[ **Skype for business server 2015topology Builder] の**順にクリックします。

7. ファイル ストアを使用するサーバーまたはプールを選び、次を行います。

8. サーバーまたはプールを右クリックし、**[プロパティの編集]** をクリックします。

9. **[プロパティの編集]** で、**[関連付け]** の **[ファイル ストア]** にある **[新規]** をクリックします。

10. **[新しいファイル ストアの定義]** の **[ファイル サーバーの FQDN]** で、ファイル サーバーの完全修飾ドメイン名 (FQDN) を入力します。**[ファイル共有]** で、新しいファイル共有のフォルダー名を入力し、**[OK]** をクリックします。

     > [!IMPORTANT]
     > この手順では、トポロジビルダーで使用する新しいファイルストアを定義します。 その定義は一度だけ行い、サーバーごとに定義する必要はありません。 トポロジを公開する前に、定義したファイル共有を、定義したファイル サーバー上に作成する必要があります。 詳細については、「[Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)」をご覧ください。

11. ファイル ストアを使用する各サーバーまたはプールでは、次を行います。

12. サーバーまたはプールを右クリックし、**[プロパティの編集]** をクリックします。

13. **[プロパティの編集]** で、**[関連付け]** の **[ファイル ストア]** で新しいファイル共有を選び **[OK]** をクリックします。

14. トポロジを公開し、レプリケーションの状態を確認します。次に、必要に応じて、Skype for Business Server 展開ウィザードを実行します。 詳しくは「[Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)」をご覧ください。

15. コマンドプロンプトを起動します。 [**スタート**] ボタンをクリックし、[ファイル名を指定して**実行**] をクリックして、cmd.exe と入力します。

16. コマンドラインで、次のように入力します。

    ```
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > /S スイッチはファイル、ディレクトリ、およびサブディレクトリをコピーします。 /XF スイッチは Meeting.Active という名前のファイルをすべてスキップします。 /MT スイッチを備えた現在のバージョンの robocopy.exe は、複数のスレッドを使用してコピーの速度を大幅に高めています。 /LOG スイッチの場合は、C:\Logfiles\log.txt. の形式でディレクトリパスとログファイル名を使用します。 このスイッチは、指定された場所で操作のログ ファイルを作成します。

17. データのコピーが完了したら、Lync Server のコントロールパネルで、[**トポロジ**] をクリックし、[**状態**] をクリックします。

18. サービスを停止した各サーバーまたはプールでは、サーバーまたはプールを選び、**[操作]**、**[すべてのサービスを開始する]** の順にクリックします。

19. 古いファイル ストアをトポロジから削除し、トポロジを公開します。詳しくは、「[Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)」をご覧ください。

20. (省略可能) 削除したファイル ストアを含むコンピューターに、ローカルの Administrators グループまたは Domain Admins グループのメンバーとしてログオンし、古いファイル共有とディレクトリを削除します。

## <a name="see-also"></a>関連項目

[別のファイルストアにサーバーを再割り当てする](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[ファイルストアを削除する](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
