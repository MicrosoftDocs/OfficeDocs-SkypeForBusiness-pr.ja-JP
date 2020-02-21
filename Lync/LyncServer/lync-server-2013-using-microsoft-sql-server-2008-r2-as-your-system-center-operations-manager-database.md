---
title: 'Lync Server 2013: Microsoft SQL Server 2008 R2 を System Center Operations Manager データベースとして使用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0001d70033aac6d7c6125bb9e4016143beefc80f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Lync Server 2013 の System Center Operations Manager データベースとしての Microsoft SQL Server 2008 R2 の使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-29_

SQL Server 2008 R2 をバックエンドデータベースとして使用するには、このトピックに記載されている手順を実行します。

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>SQL Server 2008 R2 および SQL Server Reporting Services の構成

System Center Operations Manager のインストールを開始する前に、SQL Server 2008 R2 と SQL Server Reporting Services の構成に2つの変更を加える必要があります。 (これらの変更は、SQL Server 2008 R2 を Operations Manager データベースとして使用している場合にのみ必要です)。まず、Operations Manager データベースをホストするコンピューターで、次の手順を実行します。

1.  [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

2.  [ファイル名を指定して**実行**] ダイアログボックスで、「 **C:\\Program Files\\Microsoft\\SQL Server\\\\ \_msrs10.archinst 50** 」と入力し、enter キーを押します。

3.  **ReportServer** フォルダーで、メモ帳などのテキスト エディターで **rsreportserver.config** ファイルを開きます。

4.  ファイルの先頭付近に "Add Key" ノードがいくつかあります。 ** \<[キーの追加] = "secureconnectionlevel"** を開始するエントリを見つけ、値を**0**に設定します。
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  **rsreportserver.config** ファイルを保存し、テキスト エディターを閉じます。

レポート サーバーの構成ファイルを更新したら、次は、SQL Server Reporting Services に適切な証明書を割り当てる必要があります。そのためには、次の操作を行います。

1.  [**スタート**]、 **[すべてのプログラム**]、[ **Microsoft SQL Server 2008 R2**]、[**構成ツール**] の順にクリックし、[ **Reporting Services 構成マネージャー**] をクリックします。

2.  [**Reporting Services 構成の接続**] ダイアログ ボックスの [**サーバー名**] ボックスに、サーバーの名前が表示されていることを確認します。 [**レポートサーバーインスタンス**] ドロップダウンリストから、Operations Manager データベースをホストする SQL Server インスタンス (たとえば、「 **arch inst**」) を選択し、[**接続**] をクリックします。

3.  Reporting Services 構成マネージャーで、[**Web サービスの URL**] をクリックします。

4.  [**Web サービスの URL**] ページで、Reporting Services に使用する証明書を [**SSL 証明書**] ドロップダウン リストから選択し、[**適用**] をクリックします。2 ～ 3 秒後、[**レポート サーバー Web サービスの URL**] の下に URL のペアが表示されます。

5.  両方の URL をクリックして、SQL Server Reporting Services にアクセスできることを確認します。

6.  Reporting Services 構成マネージャーを閉じます。

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>SQL Server 2008 R2 で使用する System Center Operations Manager データベースを作成する

SQL Server 2008 R2 データベースを使用するように System Center Operations Manager を構成する場合は、SQL Server 2008 R2 を実行しているコンピューターに Operations Manager データベースを手動で作成する必要があります。 (バックエンドデータベースとして SQL Server 2005 または SQL Server 2008 を使用している場合は、これらの手順は必要ありません)。

Operations Manager データベースを手動で作成するには、次の手順を実行します。

1.  System Center Operations Manager 2007 R2 セットアップメディアの SupportTools\\AMD64 フォルダーで、[ **dbcreatewizard**] をダブルクリックします。

2.  データベース構成ウィザードの [**データベース構成ウィザードの開始**] ページで、[**次へ**] をクリックします。

3.  [**データベース情報**] ページで、すべての設定をそのまま使用し (一切変更しないで)、[**次へ**] をクリックします。

4.  [**管理グループの構成**] ページで、[管理グループ**名**] ボックスに管理グループの名前 (例: **Lync Server Monitoring**) を入力し、[**次へ**] をクリックします。

5.  [**Operations Manager エラー レポート**] ページで、[**次へ**] をクリックします。

6.  [**概要**] ページで、[**完了**] をクリックします。

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>SQL Server 2008 R2 で使用する System Center Operations Manager データウェアハウスを作成する

Microsoft Lync Server 2013 には、次の3つの新しい System Center Operations Manager レポートが付属しています。

  - **エンドツーエンドシナリオの可用性レポート**   このレポートでは、登録やプレゼンスなど、主要な Lync Server サービスの可用性/稼働時間を詳細に説明します。

  - **処理能力レポート**   このレポートは、パフォーマンスカウンターの情報を使用して、メモリの可用性やプロセッサの使用率などのシステムコンポーネントの傾向を示します。

  - **コンポーネントレポート**   このレポートには、Lync Server コンポーネントによってグループ化された上位の通知ジェネレーターが一覧表示されます。

これらの新しいレポートを使用するには、System Center Operations Manager データウェアハウスをインストールする必要があります。 (データウェアハウスは、運用データの長期的な保存に使用します)。SQL Server 2008 R2 でデータウェアハウスを使用するには、SQL Server データベースをホストするコンピューターで次の手順を実行する必要があります。

1.  System Center Operations Manager セットアップメディアのセットアップ\\supporttools\\AMD64 フォルダーで、[ **dbcreatewizard**] をダブルクリックします。

2.  データベース構成ウィザードの [**データベース構成ウィザードの開始**] ページで、[**次へ**] をクリックします。

3.  [**データベース情報**] ページで、[**データベースのタイプ**] ドロップダウン リストから [**Operations Manager データ ウェアハウス データベース**] を選択し、[**次へ**] をクリックします。

4.  [**概要**] ページで、[**完了**] をクリックします。

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>System Center Operations Manager コンソールのインストール

Operations Manager コンソールは、System Center Operations Manager を管理するために使用される主要なツールです。 Operations Manager コンソールをインストールする前に、サポートされているバージョンの SQL Server と SQL Server Reporting Service がインストールされていることを確認してください。 また、SQL Server の Reporting Services 構成マネージャーを実行して、Reporting Service が正しくインストールおよび構成されていることを確認することもお勧めします。

System Center Operations Manager コンソールをインストールするには、次の操作を行います。

1.  System Center Operations Manager セットアップメディアで、[ **setupom.exe**] をダブルクリックします。

2.  System Center Operations Manager 2007 R2 セットアップで、[**前提条件の確認**] をクリックします。

3.  System Center Operations Manager の前提条件ビューアーで、インストールする System Center コンポーネントを選択します。 (**サーバー**;**コンソール**。**PowerShell**) を選択し、[**確認**] をクリックします。 ブロックの問題が報告されていないことを確認し、[**閉じる**] をクリックします。 ブロックの問題が報告された場合は、問題を修正し、[**チェック**] をクリックして、前提条件のテストを再実行します。

4.  System Center Operations Manager セットアップで、[ **Operations manager のインストール**] をクリックします。

5.  System Center Operations Manager セットアップウィザードの [ **System Center Operations Manager セットアップウィザードへようこそ**] ページで、[**次へ**] をクリックします。

6.  [**使用許諾契約書**] ページで、[**使用許諾契約書に同意します**] を選択し、[**次へ**] をクリックします。

7.  [**製品登録**] ページで、[**ユーザー名**] ボックスに自分の名前を、[**組織**] ボックスに組織の名前を入力します。 [ **25 桁の CD キーを入力**してください] ボックスに System Center Operations Manager のプロダクトキーを入力し、[**次へ**] をクリックします。

8.  [**カスタム セットアップ**] ページで、インストールする System Center オプションを選択し、[**次へ**] をクリックします。インストールする**管理サーバー**、**ユーザー インターフェイス**、および **Web コンソール**を選択する必要があります。**データベース**はインストールしないので選択しないでください。

9.  [ **SC データベースサーバーインスタンス**] ページで、Operations Manager データベースがインストールされているコンピューターの名前が [**システムセンターデータベースサーバー** ] ボックスに表示されていることを確認します。 [**次へ**] をクリックします。

10. [**管理サーバー アクション アカウント**] ページで、[**ドメインまたはローカル コンピューターのアカウント**] を選択し、[**ユーザー アカウント**]、[**パスワード**]、および [**ドメインまたはローカル コンピューター**] ボックスにそれぞれ適切な値を入力します。[**次へ**] をクリックします。

11. [**SDK と Config サービス アカウント**] ページで、[**ドメインまたはローカル コンピューターのアカウント**] を選択し、[**ユーザー アカウント**]、[**パスワード**]、および [**ドメインまたはローカル コンピューター**] ボックスにそれぞれ適切な値を入力します。[**次へ**] をクリックします。

12. [**Operations Manager エラー レポート**] ページで、[**次へ**] をクリックします。

13. [**カスタマー エクスペリエンス向上プログラム**] ページで、[**次へ**] をクリックします。

14. [**プログラムのインストールの準備完了**] ページで、[**インストール**] をクリックします。

15. [**System Center Operations Manager セットアップ ウィザードを完了しています**] ページで、[**暗号化キーのバックアップ**] および [**コンソールの開始**] チェック ボックスをオフにし、[**完了**] をクリックします。

16. System Center Operations Manager セットアップで、[**終了**] をクリックします。

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>System Center レポート サービスのインストール

System Center Operations Manager コンソールをインストールして構成した後、System Center Reporting Services をインストールする必要があります。 SQL Server 2008 R2 を Operations Manager のバックエンドデータベースとして使用している場合は、まず、SQL Server Reporting Services に関連付けられているセキュリティグループに一時的な変更を加える必要があることを意味します。 SQL Server 2008 R2 を使用している場合は、次の操作を実行する必要があります。

1.  [**スタート**] ボタンをクリックし、[**管理ツール**] をポイントします。次に [**サーバー マネージャー**] をクリックします。

2.  サーバー マネージャーで、[**構成**]、[**ローカル ユーザーとグループ**] の順に展開し、[**グループ**] をクリックします。

3.  次のグループを見つけます (ここで、atl-ws-01 はコンピューターの名前を表し、アーキテクチャ INST はシステムセンターデータベースの SQL Server インスタンスを表します。 **SQLServerReportServerUser $ atl-sc-001 $\_msrs10.archinst 50.**

4.  このグループを右クリックし、[**名前の変更**] をクリックします。 グループ名から** \_50**を削除して、グループの名前を変更します。 次に例を示します。 **SQLServerReportServerUser $ atl-sc-001 $ msrs10.archinst。アーキテクチャ (INST**)

5.  サーバー マネージャーを閉じます。

この時点で、System Center レポート サービスをインストールできます。そのためには、次の操作を行います。

1.  System Center Operations Manager 2007 R2 セットアップメディアで、 **setupom.exe**をダブルクリックします。

2.  System Center Operations Manager 2007 R2 セットアップで、[ **Operations Manager レポートのインストール**] をクリックします。

3.  System Center Operations Manager 2007 R2 レポートセットアップウィザードの [ **Operations Manager Reporting のセットアップへようこそ**] ページで、[**次へ**] をクリックします。

4.  [**使用許諾契約書**] ページで、[**使用許諾契約書に同意します**] を選択し、[**次へ**] をクリックします。

5.  [**製品登録**] ページで、[**ユーザー名**] ボックスに自分の名前が、[**組織**] ボックスに組織の名前が表示されていることを確認し、[**次へ**] をクリックします。

6.  [**カスタム セットアップ**] ページで、[**レポート サーバー**] をクリックし、[**このコンポーネントおよびすべての従属コンポーネントは、ローカル ディスク ドライブにインストールされます。**] を選択します。[**データ ウェアハウス**] をクリックし、[**インストールしない**] を選択して、[**次へ**] をクリックします。

7.  [**ルート管理サーバーに接続**] ページで、[**ルート管理サーバー**] ボックスに、Operations Manager のルート管理サーバーの名前を入力し、[**次へ**] をクリックします。

8.  [**Operations Manager のデータ ウェアハウスに接続**] ページで、[**SQL Server インスタンス**] ボックスに、データ ウェアハウスが配置される SQL Server インスタンスを入力します (データ ウェアハウスが既定のインスタンスに配置される場合は、atl-sql-001 など、サーバー名のみを入力します)。[**名前**] ボックスにデータベース名 "**OperationsManagerDW**" が表示され、[**SQL Server ポート**] ボックスに "**1433**" と表示されることを確認します。[**次へ**] をクリックします。

9.  [**SQL Server Reporting Services インスタンス**] ページで、[**SQL Server Reporting Services のサーバーを入力してください**] ドロップダウン リストから SQL Server レポート サーバーを選択し、[**次へ**] をクリックします。

10. [**データ ウェアハウス書き込みアカウント**] ページで、[**ユーザー アカウント**] および [**パスワード**] ボックスに、データ ウェアハウスに対する書き込みアクセス許可を最初に割り当てるユーザーの名前とパスワードを入力します。[**ドメイン**] ドロップダウン リストからユーザーのドメインを選択し、[**次へ**] をクリックします。

11. [**データ リーダー アカウント**] ページで、[**ユーザー アカウント**] および [**パスワード**] ボックスに、SQL Reporting Services がデータ ウェアハウスをクエリするときに使用するユーザー アカウントの名前とパスワードを入力します。[**ドメイン**] ドロップダウン リストからアカウントのドメインを選択し、[**次へ**] をクリックします。

12. [**オペレーション データ レポート**] ページで、[**次へ**] をクリックします。

13. [**Microsoft Update**] ページで、[**次へ**] をクリックします。

14. [**プログラムのインストールの準備完了**] ページで、[**インストール**] をクリックします。

15. [**Operations Manager Reporting コンポーネント セットアップ ウィザードを完了しています**] ページで、[**完了**] をクリックします。

16. System Center Operations Manager 2007 R2 セットアップで、[**終了**] をクリックします。

System Center レポートをインストールした後、次の手順を使用して、SQL Server レポートに関連付けられているセキュリティグループの名前をリセットします。 この手順は、SQL Server を使用している場合にのみ必要になります。

1.  [**スタート**] ボタンをクリックし、[**管理ツール**] をポイントします。次に [**サーバー マネージャー**] をクリックします。

2.  サーバー マネージャーで、[**構成**]、[**ローカル ユーザーとグループ**] の順に展開し、[**グループ**] をクリックします。

3.  次のグループを見つけます (atl-sc-bytes はコンピューターの名前を表し、アーキテクチャ INST はアーカイブデータベースおよび監視データベースの SQL Server インスタンスを表します。 **SQLServerReportServerUser $ atl-sc-001 $ msrs10.archinst。アーキテクチャ (INST**)

4.  このグループを右クリックし、[**名前の変更**] をクリックします。 グループ名の末尾に、SQL Server インスタンス名の直前に** \_50**を追加して、グループの名前を変更します。 次に例を示します。 **SQLServerReportServerUser $ atl-sc\_-001 $ msrs10.archinst 50mb**。

5.  サーバー マネージャーを閉じます。

System Center Operations コンソールが開いている場合は、アプリケーションをいったん閉じて再起動してください。再起動しないと、Operations コンソール ユーザー インターフェイスに [**レポート**] タブが表示されません。Operations コンソールを初めて再起動したときは、[**レポート**] タブにすべての監視レポートが表示されるまでに数分間かかることがあります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

