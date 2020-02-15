---
title: 'Lync Server 2013: ベストプラクティスアナライザーからのレポートの表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50f296fbc333f5a9e7a140c9b9d8ed18725e69a5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 のベストプラクティスアナライザーからレポートを表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

ベストプラクティスアナライザーを使用して環境をスキャンする場合は、スキャンの名前を指定します。 ベストプラクティスアナライザーはスキャンを完了した後、スキャン結果をレポートに保存し、スキャンの名前の下に保存します。 スキャンが完了すると、[スキャン**完了**] ページから直接 [**このベストプラクティススキャンのレポートを表示**] をクリックすることによって、そのスキャンに対して生成されたレポートを表示できます。 後でスキャンまたは以前のスキャンからのレポートを表示することもできます。 スキャンが実行されたローカルコンピューターのレポートを表示したり、別のコンピューターからのスキャン結果をインポートしたり、スキャン結果をエクスポートして、ベストプラクティスアナライザーがインストールされている別のコンピューターのレポートを表示したりできます。

スキャン結果は、次の種類のレポートで表示されます。

  - リスト レポート

  - ツリー レポート

  - その他のレポート

これらのレポートには、エラー、警告、およびその他の情報が含まれます。 これらの種類のレポートと問題の詳細については、「 [Lync Server 2013 のベストプラクティスアナライザーによって作成されたレポート](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md)について」を参照してください。

次の手順を使用して、ベストプラクティスアナライザーによって以前に生成されたスキャン結果を表示します。

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>以前のスキャンからのレポートを表示するには

1.  ローカルユーザーアカウントのメンバーであるアカウントを使用して、ベストプラクティスアナライザーがインストールされているコンピューターにログオンします。
    
    > [!NOTE]  
    > ローカルの Administrators グループのメンバーであるアカウントを使用してスキャンの結果を表示することはできますが、適切なユーザー権限とアクセス許可を持っていない限り、スキャンを実行することはできません。 詳細については、「 <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Lync Server 2013 のベストプラクティスアナライザーのグループメンバーシップとユーザー権限要件</A>」を参照してください。

2.  [**スタート**] をクリックし、[**すべてのプログラム**] をポイントします。次に、[ **Microsoft Lync Server 2013**] をクリックし、[**ベストプラクティスアナライザー**] をクリックします。

3.  [**ようこそ**] 画面で、[**スキャン結果を表示する**] をクリックします。

4.  [**表示するベストプラクティススキャンを選択**する] ページで、次のいずれかの手順を実行します。
    
      - ローカルに保存されたスキャン結果の一覧からレポートを表示するには、スキャンの名前をクリックしてから、[**このスキャンのレポートを表示**する] をクリックします。
        
        > [!NOTE]  
        > ベストプラクティスアナライザーによって、フォルダー &lt;systemDrive&gt;\\Documents および Settings\\&lt;user&gt;\Application data\microsoft\rtcbpa のローカルファイルの一覧が作成されます。
    
      - 別の場所に格納されているスキャンの結果のレポートを表示するには、[**スキャンのインポート**] をクリックし、スキャン結果を含むファイルを見つけて、[**開く**] をクリックします。
        
        > [!NOTE]  
        > このコンピューターのベストプラクティスアナライザーのバージョンが、インポートされたファイル内のデータの収集に使用されたバージョンと一致しない場合、コンピューター上のツールはインポート後にファイルを再び分析する可能性があります。

5.  [**View Best Practices Report**] ページで、次のいずれかの操作を行います。
    
      - 各レポートをサーバー コンポーネント別に分類してリストに表示するには、[**List Reports**] をクリックし、[**All Issues**] タブまたは [**Informational Items**] タブのどちらかをクリックします。
    
      - 各レポートを結果の種類別に分類した階層リストとして表示するには、[**Tree Reports**] をクリックし、[**Detailed View**] タブまたは [**Summary View**] タブのどちらかをクリックします。
    
      - その他のレポートを表示するには、[**Other Reports**] をクリックします。
    
    > [!NOTE]  
    > ベストプラクティスアナライザーのレポートと、そのレポートで特定される問題の詳細については、「 <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Lync server 2013 のベストプラクティスアナライザーによって作成されたレポートの表示と操作</A>」および「 <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">lync server 2013 でのベストプラクティスアナライザーによって識別される問題の分析と解決</A>」を参照してください。

</div>

</div>

</div>

</div>

</div>

