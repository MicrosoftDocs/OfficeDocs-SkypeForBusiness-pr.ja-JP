---
title: Skype for Business Server 2015 での新しいファイル ストアへのファイル ストア データの移動
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/30/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: サーバー 2015 のビジネス展開に、Skype のファイル ストアとしての機能になっているファイル サーバーを削除する必要がありますかは、現在の変更を保存使用できないその他のために必要な場合、新しい共有を作成する必要があります。 次の手順を実行する必要があります。
ms.openlocfilehash: 364b63c1c93ed9a817596cb90cbe1ea92198a514
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888333"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>Move File Store Data to a New File Store in Skype for Business Server 2015

サーバー 2015 のビジネス展開に、Skype のファイル ストアとしての機能になっているファイル サーバーを削除する必要がありますかは、現在の変更を保存使用できないその他のために必要な場合、新しい共有を作成する必要があります。 次の手順を実行する必要があります。

1. サーバー 2015 のビジネス サービスを削除するファイル ストアを使用するの Skype を終了します。

2. トポロジ ビルダーのファイル ストアを定義し、格納する新しいファイルを展開で使用できるようにするのには変更を公開します。

3. 新しいファイル ストアにデータを移行します。

4. サーバーまたはサービスを再起動します。

5. オプションで、古いファイル共有とファイル フォルダーを削除します。

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>ファイル ストアのデータを新しいファイル ストアに移動するには

1. ビジネス サーバー 2015、管理ツールの Skype がインストールされている RTCUniversersalServerAdmins または CsServerAdministrator のグループのメンバーとしてコンピューターにログオンします。

2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。

3. 左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。

4. 各ディレクター プール、ディレクター、Standard Edition サーバー、およびフロント エンド プールを削除するファイル ストアを使用する、サーバーまたはプールを選択して**アクション**を**すべてのサービスの停止**] をクリックします。

5. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

6. 開始トポロジ ビルダー: [**スタート**] ボタン [**すべてのプログラム**] をクリックして、**ビジネス サーバー 2015 の Skype**を**Skype ビジネス サーバー 2015Topology ビルダー**] をクリックします。

7. ファイル ストアを使用するサーバーまたはプールを選び、次を行います。

8. サーバーまたはプールを右クリックし、**[プロパティの編集]** をクリックします。

9. **[プロパティの編集]** で、**[関連付け]** の **[ファイル ストア]** にある **[新規]** をクリックします。

10. **[新しいファイル ストアの定義]** の **[ファイル サーバーの FQDN]** で、ファイル サーバーの完全修飾ドメイン名 (FQDN) を入力します。**[ファイル共有]** で、新しいファイル共有のフォルダー名を入力し、**[OK]** をクリックします。

     > [!IMPORTANT]
     > この手順では、トポロジ ビルダーで使用するための新しいファイル ストアを定義します。 その定義は一度だけ行い、サーバーごとに定義する必要はありません。 トポロジを公開する前に、定義したファイル共有を、定義したファイル サーバー上に作成する必要があります。 詳細については、「[Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)」をご覧ください。

11. ファイル ストアを使用する各サーバーまたはプールでは、次を行います。

12. サーバーまたはプールを右クリックし、**[プロパティの編集]** をクリックします。

13. **[プロパティの編集]** で、**[関連付け]** の **[ファイル ストア]** で新しいファイル共有を選び **[OK]** をクリックします。

14. トポロジを公開、レプリケーション ・ ステータスをチェックして、Skype、必要に応じてビジネス サーバーの展開ウィザードを実行しています。 詳しくは「[Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)」をご覧ください。

15. コマンド プロンプトを起動します。 [**スタート**] ボタン**を実行**するには、をクリックし、cmd.exe と入力します。

16. コマンドラインで、次のように入力します。

    ```
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > /S スイッチはファイル、ディレクトリ、およびサブディレクトリをコピーします。 /XF スイッチは Meeting.Active という名前のファイルをすべてスキップします。 /MT スイッチを備えた現在のバージョンの robocopy.exe は、複数のスレッドを使用してコピーの速度を大幅に高めています。 /LOG スイッチ、C:\Logfiles\log.txt の形式でディレクトリ パスとログ ファイル名を使用します。 このスイッチは、指定された場所で操作のログ ファイルを作成します。

17. データのコピーが完了すると、Lync Server コントロール パネルでは、**トポロジ**をクリックし、**状態**] をクリックします。

18. サービスを停止した各サーバーまたはプールでは、サーバーまたはプールを選び、**[操作]**、**[すべてのサービスを開始する]** の順にクリックします。

19. 古いファイル ストアをトポロジから削除し、トポロジを公開します。詳しくは、「[Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)」をご覧ください。

20. (省略可能) 削除したファイル ストアを含むコンピューターに、ローカルの Administrators グループまたは Domain Admins グループのメンバーとしてログオンし、古いファイル共有とディレクトリを削除します。

## <a name="see-also"></a>関連項目

[別のファイル ストアへのサーバーの再割り当てください。](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[ファイル ストアを削除します。](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
