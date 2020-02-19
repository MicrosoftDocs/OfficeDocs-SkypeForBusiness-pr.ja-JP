---
title: ベストプラクティスアナライザーを使用して展開をスキャンし、潜在的な問題を検出する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6c3c2c5b49ae59c93ac6f78a2ae354061d7bf0d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>ベストプラクティスアナライザーを使用して Lync Server 2013 の展開で問題が発生する可能性のある問題をスキャンする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-21_

ベスト プラクティス アナライザーのスキャンを実行する場合は、次の指定を行う必要があります。

  - **資格情報**   スキャンを実行するには、ローカルの Administrators グループのメンバーであるアカウントを使用して、ベストプラクティスアナライザーがインストールされているコンピューターにログオンする必要があります。 また、ログオンに使用するユーザー アカウントには、適切なスキャンを実行するために必要なユーザー権限とアクセス許可が割り当てられているか、ベスト プラクティス アナライザーの実行時に適切なユーザー権限とアクセス許可を持つ資格情報を指定する必要があります。 詳細については、「 [Lync Server 2013 のベストプラクティスアナライザーのグループメンバーシップとユーザー権限要件](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md)」を参照してください。

  - **スキャンのスコープ**   スキャンの範囲を指定するには、スキャンするカテゴリとサーバーを選択します。 Lync Server 環境では、特定のカテゴリ内のすべてのカテゴリ、1つ以上のカテゴリ、または1つ以上のサーバーを選択できます。

  - **スキャンの種類**   現時点では、正常性チェックスキャンは利用可能な唯一の種類のスキャンです (既定で選択されています)。 正常性チェックでは、範囲内で指定されたすべてのサーバーを対象として、エラー、警告、およびその他の情報を示すレポートが生成されます。

  - **ネットワーク速度**   のネットワーク速度のオプションには、高速 lan (100 mbps 以上)、LAN (10 mbps)、高速 WAN (1.5 Mbps)、または wan (64 kbps) があります。 スキャンの実行にかかる推定時間は、この設定に基づいて算出されます。 また、この設定はタイムアウト時間の設定にも使用されます。 スキャンの実行中、ベスト プラクティス アナライザーは、サーバーから応答が返るのを指定時間内待ちます。 その間に応答が返らなかった場合、ベスト プラクティス アナライザーは、次のサーバーのスキャンに移ります。 低速のネットワークでは、指定されるタイムアウト時間がより長くなるため、ネットワーク待ち時間が長くなります。 ベスト プラクティス アナライザーが短時間でタイムアウトすることがないように、このパラメーターにはトポロジ内で最も低速のリンクを選択することをお勧めします。

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>Lync Server 2013 の展開をスキャンするには

1.  ベスト プラクティス アナライザーがインストールされているコンピューターにログオンします。このログオンに使用するアカウントは、ローカルの Administrators グループのメンバーで、かつその他必要なユーザー権限とアクセス許可を持っている必要があります。

2.  [**スタート**] をクリックし、[**すべてのプログラム**] をポイントします。次に、[ **Microsoft Lync Server 2013**] をクリックし、[**ベストプラクティスアナライザー**] をクリックします。

3.  [**Welcome**] 画面で、[**Select options for a new scan**] をクリックします。

4.  [**Connect to Active Directory**] ページで、[**Active Directory Server**] に指定されている名前を確認し、次の操作を行います。
    
      - コンピューターへのログオンに使用した資格情報を使用してスキャンするには、[**Connect to the Active Directory server**] をクリックします。
    
      - Active Directory ドメイン サービス、エッジ サーバー、または Exchange Server に使用する別の資格情報を指定するには、[**Show advanced logon options**] をクリックし、必要な資格情報を示すチェック ボックスを個々にオンにします。次に、オンにした各チェック ボックスの資格情報を指定し、[**Connect to the Active Directory server**] をクリックします。
    
    <div>
    

    > [!NOTE]
    > スキャンを開始する前に、ベスト プラクティス アナライザーはネットワークとアクセス許可のチェックを実行して、指定されたアカウント資格情報が有効で、ベスト プラクティス アナライザーが Active Directory ドメイン サービスに接続できるかどうかを確認します。ベスト プラクティス アナライザーをワークグループ サーバー上で実行すると、ベスト プラクティス アナライザーが境界ネットワーク内にあるエッジ サーバーに接続できるかどうか (つまり、これらのエッジ サーバーがスキャンに含まれるかどうか) も確認されます。

    
    </div>

5.  [**Start a new Best Practices scan**] ページで、スキャンに含めるオプションを選択し、ネットワークの速度を指定して、[**Start scanning**] をクリックします。

6.  [**Scanning Completed**] ページで、[**View a report of this Best Practices scan**] をクリックします。

7.  [**View Best Practices Report**] ページで、次のいずれかの操作を行います。
    
      - 各レポートをサーバー コンポーネント別に分類してリストに表示するには、[**List Reports**] をクリックし、[**All Issues**] タブまたは [**Informational Items**] タブのどちらかをクリックします。
    
      - 各レポートを結果の種類別に分類した階層リストとして表示するには、[**Tree Reports**] をクリックし、[**Detailed View**] タブまたは [**Summary View**] タブのどちらかをクリックします。
    
      - その他のレポートを表示するには、[**Other Reports**] をクリックします。
    
    <div>
    

    > [!NOTE]
    > ベストプラクティスアナライザーのレポートと、そのレポートで特定される問題の詳細については、「 <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Lync server 2013 のベストプラクティスアナライザーによって作成されたレポートの表示と操作</A>」および「 <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">lync server 2013 でのベストプラクティスアナライザーによって識別される問題の分析と解決</A>」を参照してください。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

