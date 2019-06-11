---
title: 'Lync Server 2013: ベストプラクティスアナライザーからレポートを表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb2c229d683ecd0dcf4fee94b456514527226152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 のベストプラクティスアナライザーからレポートを表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

ベストプラクティスアナライザーを使って環境をスキャンする場合は、スキャンの名前を指定します。 ベストプラクティスアナライザーがスキャンを完了した後、スキャン結果はレポートに保存され、スキャンの名前の下に保存されます。 スキャンが完了したら、[スキャン**完了**] ページから直接 [**このベストプラクティススキャンのレポートを表示**] をクリックして、スキャン用に生成されたレポートを表示できます。 また、そのスキャンまたは前のスキャンのレポートを後で表示することもできます。 スキャンが実行されたローカルコンピューターのレポートを表示したり、別のコンピューターからスキャン結果をインポートしたり、スキャン結果をエクスポートして、ベストプラクティスアナライザーがインストールされている別のコンピューターでレポートを表示したりできます。

スキャン結果は、次の種類のレポートで示されます。

  - リストレポート

  - ツリーレポート

  - その他のレポート

これらのレポートには、エラー、警告、その他の情報が含まれます。 これらの各種類のレポートと問題の詳細については、「 [Lync Server 2013 のベストプラクティスアナライザーで作成されたレポートについ](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md)て」を参照してください。

次の手順を使用して、ベストプラクティスアナライザーによって以前に生成されたスキャン結果を表示します。

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>以前のスキャンのレポートを表示するには

1.  ローカルユーザーアカウントのメンバーであるアカウントを使用して、ベストプラクティスアナライザーがインストールされているコンピューターにログオンします。
    
    > [!NOTE]  
    > ローカル管理者グループのメンバーであるアカウントを使用してスキャンの結果を表示することはできますが、適切なユーザー権限と権限がない限り、スキャンを実行することはできません。 詳細については、「 <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Lync Server 2013 のベストプラクティスアナライザーのグループメンバーシップとユーザー権利の要件</A>」を参照してください。

2.  [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[**ベストプラクティスアナライザー**] の順にクリックします。

3.  [**ようこそ**] 画面で、[**スキャン結果を表示する**] をクリックします。

4.  **[表示するベストプラクティススキャンを選択**する] ページで、次のいずれかの操作を行います。
    
      - ローカルに保存されているスキャン結果の一覧からレポートを表示するには、スキャンの名前をクリックし、[**このスキャンのレポートを表示**] をクリックします。
        
        > [!NOTE]  
        > ベストプラクティスアナライザーは、フォルダー &lt;systemDrive&gt;\\ドキュメントと設定\\&lt;ユーザー&gt;\Application Data\Microsoft\RtcBPA. からローカルファイルの一覧を作成します。
    
      - 別の場所に保存されているスキャン結果のレポートを表示するには、[**スキャンのインポート**] をクリックし、スキャン結果が含まれているファイルを見つけて、[**開く**] をクリックします。
        
        > [!NOTE]  
        > このコンピューターのベストプラクティスアナライザーのバージョンが、インポートされたファイルのデータを収集するために使用したバージョンと一致しない場合、コンピューターのツールは、インポート後にファイルをもう一度分析する可能性があります。

5.  [**ベストプラクティスレポートの表示**] ページで、次のいずれかの操作を行います。
    
      - サーバーコンポーネントによって整理されたリストのレポートを表示するには、[**リストレポート**] をクリックし、[**すべての問題**] タブまたは [**情報アイテム**] タブのいずれかをクリックします。
    
      - 結果の種類によって整理された階層リストとしてレポートを表示するには、[**ツリーレポート**] をクリックし、[**詳細表示**] タブまたは [**概要ビュー** ] タブのいずれかをクリックします。
    
      - 他のレポートを表示するには、[**その他のレポート**] をクリックします。
    
    > [!NOTE]  
    > ベストプラクティスアナライザーレポートとその報告される問題の詳細については、「 <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Lync Server 2013 のベストプラクティスアナライザーによって作成されたレポートの表示と操作</A>」と「<A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">ベストプラクティスによって識別される問題の分析と解決」を参照してください。Lync Server 2013 のアナライザー</A>

</div>

</div>

</div>

</div>

</div>

