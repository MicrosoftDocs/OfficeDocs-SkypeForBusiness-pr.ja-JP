---
title: 'Lync Server 2013: System Center Operations Manager データベースとして Microsoft SQL Server 2008 R2 を使用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 858134b4d7f2a2fbc4e15c14e121ac12679c9ddc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Lync Server 2013 の System Center Operations Manager データベースとして Microsoft SQL Server 2008 R2 を使用する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-29_

SQL Server 2008 R2 をバックエンドデータベースとして使用するには、このトピックで説明する手順を実行します。

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>SQL Server 2008 R2 と SQL Server Reporting Services の構成

System Center Operations Manager のインストールを開始する前に、SQL Server 2008 R2 と SQL Server Reporting Services の構成に2つの変更を行う必要があります。 (これらの変更は、SQL Server 2008 R2 を Operations Manager データベースとして使用している場合にのみ必要です)。まず、Operations Manager データベースをホストするコンピューターで、次の操作を行います。

1.  [**スタート**] をクリックし、[**実行**] をクリックします。

2.  [ファイル名を指定して**実行**] ダイアログボックスで、「 **C:\\Program Files\\Microsoft\\SQL Server\\\\ \_MSRS10 50.** 」と入力して、enter キーを押します。

3.  [ **ReportServer** ] フォルダーで、メモ帳またはその他のテキストエディターでファイル**rsreportserver**を開きます。

4.  ファイルの先頭付近には、一連の「追加キー」ノードが表示されます。 ** \<"キーの追加"** を開始するエントリを見つけて、値を**0**に設定します。
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  ファイルの**rsreportserver**を保存し、テキストエディターを閉じます。

レポートサーバーの構成ファイルを更新した後、SQL Server Reporting Services に適切な証明書を割り当てる必要があります。 目的:

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft SQL Server 2008 R2**]、[**構成ツール**]、[ **Reporting Services 構成マネージャー**] の順にクリックします。

2.  [ **Reporting Services の構成接続**] ダイアログボックスで、[**サーバー名**] ボックスにサーバー名が表示されていることを確認します。 [**レポートサーバーインスタンス**] ドロップダウンリストから Operations Manager データベース (例: **arch inst**) をホストする SQL Server インスタンスを選び、[**接続**] をクリックします。

3.  Reporting Services 構成マネージャーで、[ **Web サービスの URL**] をクリックします。

4.  [ **Web サービスの URL** ] ページで、[ **SSL 証明書**] ドロップダウンリストから、Reporting Services に使用する証明書を選び、[**適用**] をクリックします。 数秒後に、[**レポートサーバー Web サービス url**] の下に表示される url のペアが表示されます。

5.  両方の Url をクリックして、SQL Server Reporting Services にアクセスできることを確認します。

6.  Reporting Services 構成マネージャーを閉じます。

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>SQL Server 2008 R2 で使用する System Center Operations Manager データベースを作成する

SQL Server 2008 R2 データベースを使用するように System Center Operations Manager を構成する場合は、SQL Server 2008 R2 を実行しているコンピューターで Operations Manager データベースを手動で作成する必要があります。 (ここでも、バックエンドデータベースとして SQL Server 2005 または SQL Server 2008 を使用している場合は、この手順は必要ありません)。

Operations Manager データベースを手動で作成するには、次の手順を実行します。

1.  System Center Operations Manager 2007 R2 セットアップメディアの SupportTools\\AMD64 フォルダーで、 **dbcreatewizard .exe**をダブルクリックします。

2.  データベース構成ウィザードの [**データベース構成ウィザードへようこそ**] ページで、[**次へ**] をクリックします。

3.  [**データベース情報**] ページで、すべての設定をそのままにして、[**次へ**] をクリックします。

4.  [**管理グループの構成**] ページで、[管理グループ**名**] ボックスに管理グループの名前 (「 **Lync Server Monitoring**」など) を入力し、[**次へ**] をクリックします。

5.  [ **Operations Manager エラーレポート**] ページで、[**次へ**] をクリックします。

6.  [**概要**] ページで [**完了**] をクリックします。

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>SQL Server 2008 R2 で使用する System Center Operations Manager データウェアハウスの作成

Microsoft Lync Server 2013 には、次の3つの新しい System Center Operations Manager レポートが付属しています。

  - **[終了-終了] シナリオの可用性レポート**   このレポートは、登録やプレゼンスなどの、主要な Lync Server サービスの可用性/稼働時間を詳細に説明します。

  - ****   [パフォーマンスカウンター情報を使用したキャパシティレポート] このレポートには、メモリの可用性やプロセッサ使用率などのシステムコンポーネントの傾向が表示されます。

  - **[コンポーネントレポート**   このレポートには、Lync Server コンポーネントによってグループ化された最上位の通知ジェネレーターが一覧表示されます。

これらの新しいレポートを使用するには、System Center Operations Manager データウェアハウスをインストールする必要があります。 (データウェアハウスは、運営データの長期的なストレージに使用されます)。SQL Server 2008 R2 でデータウェアハウスを使用するには、SQL Server データベースをホストしているコンピューターで次の手順を実行する必要があります。

1.  System Center Operations Manager セットアップメディアの Setup\\supporttools\\AMD64 フォルダーで、 **dbcreatewizard .exe**をダブルクリックします。

2.  データベース構成ウィザードの [**データベース構成ウィザードへようこそ**] ページで、[**次へ**] をクリックします。

3.  [**データベース情報**] ページで、[**データベースの種類**] ドロップダウンリストから [ **Operations Manager データウェアハウスデータベース**] を選択し、[**次へ**] をクリックします。

4.  [**概要**] ページで [**完了**] をクリックします。

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>System Center Operations Manager コンソールをインストールする

Operations Manager コンソールは、System Center Operations Manager を管理するために使用される主要なツールです。 Operations Manager コンソールをインストールする前に、サポートされているバージョンの SQL Server と SQL Server Reporting Services をインストールしていることを確認してください。 また、SQL Server Reporting Services 構成マネージャーを実行して、レポートサービスが正しくインストールされ構成されていることを確認することをお勧めします。

System Center Operations Manager コンソールをインストールするには、次の操作を行います。

1.  System Center Operations Manager のセットアップメディアで、 **SetupOM**をダブルクリックします。

2.  System Center Operations Manager 2007 R2 のセットアップで、[**前提条件の確認**] をクリックします。

3.  System Center Operations Manager の前提条件ビューアーで、インストールする System Center コンポーネントを選択します。 (**サーバー**;**本体**;と**PowerShell**) を選び、[**確認**] をクリックします。 ブロッキングの問題が報告されていないことを確認し、[**閉じる**] をクリックします。 ブロッキングの問題が報告された場合は、問題を修正し、[**確認**] をクリックして、前提条件のテストを再実行します。

4.  System Center Operations Manager のセットアップで、[ **Operations manager のインストール**] をクリックします。

5.  System Center Operations Manager のセットアップウィザードの [ **System Center Operations Manager セットアップウィザードへようこそ**] ページで、[**次へ**] をクリックします。

6.  [**エンドユーザーライセンス契約**] ページで、[**使用許諾契約書の条項に同意**します] を選び、[**次へ**] をクリックします。

7.  [**製品の登録**] ページで、[**ユーザー名**] ボックスに名前を入力し、[**組織**] ボックスに組織の名前を入力します。 [ **25 桁の CD キーを入力**してください] ボックスに System Center Operations Manager のプロダクトキーを入力し、[**次へ**] をクリックします。

8.  [**カスタムセットアップ**] ページで、インストールする System Center のオプションを選択し、[**次へ**] をクリックします。 [**管理サーバー**]、[**ユーザーインターフェイス**]、[ **Web コンソール**] を選択してインストールする必要があります。 選択されていないため、**データベース**をインストールすることはできません。

9.  [ **SC Database Server インスタンス**] ページで、Operations Manager データベースがインストールされているコンピューターの名前が [ **System Center Database server** ] ボックスに表示されていることを確認します。 [ **次へ**] をクリックします。

10. [ **Management Server アクションアカウント**] ページで、 **[ドメインまたはローカルコンピューターアカウント**] を選び、[**ユーザーアカウント**] ボックス、[**パスワード**] ボックス、[**ドメインまたはローカルコンピューター** ] ボックスに適切な値を入力します。 [ **次へ**] をクリックします。

11. [ **SDK と構成サービスアカウント**] ページで [**ドメインまたはローカルコンピューターアカウント**] を選び、[**ユーザーアカウント**] ボックス、[**パスワード**] ボックス、[**ドメインまたはローカルコンピューター** ] ボックスに適切な値を入力します。 [ **次へ**] をクリックします。

12. [ **Operations Manager エラーレポート**] ページで、[**次へ**] をクリックします。

13. [**カスタマーエクスペリエンス向上プログラム**] ページで、[**次へ**] をクリックします。

14. [**プログラムをインストールする準備ができ**ました] ページで、[**インストール**] をクリックします。

15. [ **System Center Operations Manager のセットアップを完了**します] ページで、[**バックアップ暗号化キー** ] をオフにし、**コンソールのチェックボックス**をオンにしてから、[**完了**] をクリックします。

16. System Center Operations Manager のセットアップで、[**終了**] をクリックします。

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>System Center Reporting Services をインストールする

System Center Operations Manager コンソールをインストールして構成した後、System Center Reporting Services をインストールする必要があります。 SQL Server 2008 R2 を Operations Manager バックエンドデータベースとして使用している場合は、SQL Server Reporting Services に関連付けられているセキュリティグループに一時的な変更を行う必要があることを意味します。 SQL Server 2008 R2 を使用している場合は、次の手順を実行する必要があります。

1.  [**スタート**] をクリックし、[**管理ツール**] をポイントして、[**サーバーマネージャー**] をクリックします。

2.  サーバーマネージャーで、[**構成**] を展開し、[**ローカルユーザーとグループ**] を展開して、[**グループ**] をクリックします。

3.  次のグループを見つけます (atl-sc.exe はコンピューターの名前を表します)。また、システムセンターデータベースの SQL Server インスタンスは、 **SQLServerReportServerUser $ atl-sc-001 $\_MSRS10 50mb)** を参照してください。

4.  グループを右クリックし、[**名前の変更**] をクリックします。 グループ名から** \_50**を削除して、グループの名前を変更します。 例: **SQLServerReportServerUser $ atl-sc-001 $ MSRS10。ARCH**

5.  サーバーマネージャーを閉じます。

この時点で、System Center Reporting Services をインストールする準備ができました。 その手順は次のとおりです。

1.  System Center Operations Manager 2007 R2 セットアップメディアで、 **SetupOM**をダブルクリックします。

2.  System Center Operations Manager 2007 R2 のセットアップで、[ **Operations Manager レポートのインストール**] をクリックします。

3.  System Center Operations Manager 2007 R2 レポートセットアップウィザードの [ **Operations Manager reporting のセットアップへようこそ**] ページで、[**次へ**] をクリックします。

4.  [**エンドユーザーライセンス契約**] ページで、[**使用許諾契約書に同意**します] を選択し、[**次へ**] をクリックします。

5.  [**製品の登録**] ページで、自分の名前と組織の名前が [**ユーザー名**] ボックスと [**組織**名] ボックスに表示されていることを確認し、[**次へ**] をクリックします。

6.  [**カスタムセットアップ**] ページで、[ **Reporting Server** ] をクリックし、[このコンポーネント] を選択します。**すべての依存コンポーネントはローカルディスクドライブにインストールされ**ます。 [**データウェアハウス**] をクリックし、[**このコンポーネントは使用できません**] を選択し、[**次へ**] をクリックします。

7.  [**ルート管理サーバーに接続する**] ページで、[**ルート管理サーバー** ] ボックスに Operations Manager ルート管理サーバーの名前を入力し、[**次へ**] をクリックします。

8.  [ **Operations Manager データウェアハウスに接続する**] ページで、[ **sql server インスタンス**] ボックスにデータウェアハウスが配置されている sql server インスタンスを入力します。 (データウェアハウスが既定のインスタンスに配置されている場合は、サーバー名を入力します。例: atl-sql-dmo)。[**名前**] ボックスに**** データベース名の [サーバー名] が表示されていることを確認します。その場合は、[ **SQL Server のポート**] ボックスに "port **1433** " と表示されます。 [ **次へ**] をクリックします。

9.  [ **Sql Server Reporting インスタンス**] ページで、[ **Sql Server reporting Services サーバーの入力**] ドロップダウンリストから SQL Server reporting Server を選び、[**次へ**] をクリックします。

10. [**データウェアハウスの書き込みアカウント**] ページで、[**ユーザーアカウント**] ボックスと [**パスワード**] ボックスに、データウェアハウスへの書き込みアクセス許可を最初に割り当てるユーザーの名前とパスワードを入力します。 [ **Domain** ] ドロップダウンリストからユーザーのドメインを選び、[**次へ**] をクリックします。

11. [**データリーダーアカウント**] ページで、SQL Reporting Services が [**ユーザーアカウント**] ボックスと [**パスワード**] ボックスにデータウェアハウスを照会するときに使用する、ユーザーアカウントの名前とパスワードを入力します。 [ **Domain** ] ドロップダウンリストからアカウントドメインを選び、[**次へ**] をクリックします。

12. [**オペレーションデータレポート**] ページで、[**次へ**] をクリックします。

13. [ **Microsoft Update** ] ページで、[**次へ**] をクリックします。

14. [**プログラムをインストールする準備ができ**ました] ページで、[**インストール**] をクリックします。

15. [ **Operations Manager レポートコンポーネントのセットアップウィザードを完了**します] ページで、[**完了**] をクリックします。

16. System Center Operations Manager 2007 R2 のセットアップで、[**終了**] をクリックします。

System Center レポートをインストールした後、次の手順を使用して、SQL Server レポートに関連付けられているセキュリティグループの名前をリセットします。 この手順は、SQL Server を使用している場合にのみ必要です。

1.  [**スタート**] をクリックし、[**管理ツール**] をポイントして、[**サーバーマネージャー**] をクリックします。

2.  サーバーマネージャーで、[**構成**] を展開し、[**ローカルユーザーとグループ**] を展開して、[**グループ**] をクリックします。

3.  次のグループを見つけます。ここでは、atl-sc-001 はコンピューターの名前を表し、 **SQLServerReportServerUser $ atl-sc-001 $ MSRS10 の SQL Server インスタンスを示しています。ARCH**

4.  グループを右クリックし、[**名前の変更**] をクリックします。 グループ名の末尾に SQL Server インスタンス名の直前に** \_50**を追加して、グループの名前を変更します。 たとえば、 **SQLServerReportServerUser $ atl-sc-001 $ MSRS10\_50mb**。

5.  サーバーマネージャーを閉じます。

System Center Operations コンソールが開いている場合は、アプリケーションを終了して再起動する必要があります。この操作を行わない場合、[**レポート**] タブは [オペレーション] コンソールのユーザーインターフェイスに表示されません。 初めて操作コンソールを再起動した後、[**レポート**] タブにすべての監視レポートが表示されるまでに数分かかることがあります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

