---
title: ベストプラクティスアナライザーを使用して展開をスキャンし、潜在的な問題がないか確認する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c7d881ebc35a4f56207fedaa8533f0a3df3c7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>ベストプラクティスアナライザーを使用して Lync Server 2013 の展開をスキャンし、潜在的な問題を検出する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-21_

ベストプラクティスアナライザースキャンを実行するには、次のように指定する必要があります。

  - **資格情報**   スキャンを実行するには、ローカル管理者グループのメンバーであるアカウントを使用して、ベストプラクティスアナライザーがインストールされているコンピューターにログオンする必要があります。 さらに、適切なスキャンを実行するために必要なユーザー権限とアクセス許可を持つユーザーアカウントを使用してログオンするか、ベストプラクティスアナライザーを実行するときに適切なユーザー権限とアクセス許可を持つ資格情報を指定する必要があります。 詳細については、「 [Lync Server 2013 のベストプラクティスアナライザーのグループメンバーシップとユーザー権利の要件](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md)」を参照してください。

  - **スキャンのスコープ**   スキャンの範囲を指定するには、スキャンするカテゴリとサーバーを選びます。 Lync Server 環境の特定のカテゴリ内のすべてのカテゴリ、1つ以上のカテゴリ、または1つ以上のサーバーを選ぶことができます。

  - ****   現在、スキャンの種類は [正常性チェックスキャン] のみです (既定で選択されています)。 正常性チェックスキャンでは、スコープで指定されたすべてのサーバーのエラー、警告、その他の情報を含むレポートが生成されます。

  - **ネットワーク速度**   のネットワーク速度オプションには、高速 lan (100 mbps 以上)、lan (10 mbps)、高速 WAN (1.5 mbps)、または wan (64 kbps) があります。 スキャンを完了するための推定時間は、この設定に基づいています。 この設定は、タイムアウト期間を設定するためにも使用されます。 スキャン中は、ベストプラクティスアナライザーは、指定した時間、サーバーからの応答を待ちます。 指定した期間内に応答を受け取らない場合は、スキャンの次のサーバーに移動します。 低速のネットワークでは、この指定されたタイムアウト期間は長いネットワーク待ち時間を考慮しています。 このパラメーターのトポロジで最も低速のリンクを選択して、ツールが短時間でタイムアウトしないようにすることをお勧めします。

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>Lync Server 2013 の展開をスキャンするには

1.  [ローカル管理者] グループのメンバーであり、他に必要なユーザー権限と権限があるアカウントを使用して、ベストプラクティスアナライザーがインストールされているコンピューターにログオンします。

2.  [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[**ベストプラクティスアナライザー**] の順にクリックします。

3.  [**ようこそ**] 画面で、[**新しいスキャンのオプションを選択**します] をクリックします。

4.  [ **Active directory に接続する**] ページで、[ **active directory Server**] で指定された名前を確認し、次のいずれかの操作を行います。
    
      - コンピューターにログオンするために使用した資格情報を使ってスキャンを実行するには、[ **Active Directory サーバーに接続**する] をクリックします。
    
      - Active Directory ドメインサービス、エッジサーバー、または Exchange Server に使用する別の資格情報を指定するには、[**詳細なログオンオプションの表示**] をクリックし、個別の資格情報が必要な各チェックボックスをオンにして、資格情報を指定します。選択されているチェックボックスごとに、[ **Active Directory サーバーに接続する**] をクリックします。
    
    <div>
    

    > [!NOTE]
    > スキャンを開始する前に、ベストプラクティスアナライザーがネットワークとアクセス許可のチェックを実行して、指定されたアカウントの資格情報が有効であり、ベストプラクティスアナライザーが Active Directory ドメインサービスに接続できることを確認します。 ツールがワークグループサーバー上で実行されている場合は、ツールは境界ネットワーク (スキャンに含まれている場合) でエッジサーバーに接続できるかどうかも確認します。

    
    </div>

5.  [**新しいベストプラクティススキャンを開始**する] ページで、スキャンに含めるオプションを選択し、ネットワークの速度を指定して、[**スキャンの開始**] をクリックします。

6.  [**スキャンが完了しました**] ページで、[**このベストプラクティススキャンのレポートを表示**します] をクリックします。

7.  [**ベストプラクティスレポートの表示**] ページで、次のいずれかの操作を行います。
    
      - サーバーコンポーネントによって整理されたリストのレポートを表示するには、[**リストレポート**] をクリックし、[**すべての問題**] タブまたは [**情報アイテム**] タブのいずれかをクリックします。
    
      - 結果の種類によって整理された階層リストとしてレポートを表示するには、[**ツリーレポート**] をクリックし、[**詳細表示**] タブまたは [**概要ビュー** ] タブのいずれかをクリックします。
    
      - 他のレポートを表示するには、[**その他のレポート**] をクリックします。
    
    <div>
    

    > [!NOTE]
    > ベストプラクティスアナライザーレポートとその報告事項について詳しくは、「 <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Lync Server 2013 でのベストプラクティスアナライザーによって作成されたレポートの表示と操作</A>」と「<A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">ベストプラクティスアナライザーによって識別される問題の分析と解決」をご覧ください。Lync Server 2013 の</A>場合。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

