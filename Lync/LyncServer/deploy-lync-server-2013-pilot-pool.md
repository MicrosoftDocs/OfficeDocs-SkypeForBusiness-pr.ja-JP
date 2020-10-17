---
title: Lync Server 2013 パイロットプールの展開
description: Lync Server 2013 パイロットプールを展開します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a599cee1719f773ebbf3cf5a71405aa9b7259261
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550793"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a>Lync Server 2013 パイロットプールの展開

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-22_

Lync Server 2013 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。 パイロットプールは、lync server 2013 と Lync Server 2010 の展開との共存をテストする場所です。 共存は、すべてのユーザーとプールを Lync Server 2013 に移動するまで、一時的な状態になります。

パイロット プールを展開するときには、新しいフロントエンド プールの定義ウィザードを使用します。 Lync server 2010 プールにある、Lync Server 2013 パイロットプールと同じ機能とワークロードを展開する必要があります。 アーカイブサーバー、監視サーバー、または System Center Operations Manager を使用して Lync Server 2010 環境をアーカイブまたは監視する場合に、移行を通じてアーカイブまたは監視を続行するには、これらの機能をパイロット環境に展開する必要があります。 Lync Server 2010 環境をアーカイブまたは監視するために展開したバージョンは、Lync Server 2013 環境のデータをキャプチャしません。

<div>


> [!NOTE]  
> 次の手順では、パイロット プール全体の展開プロセスの中で検討する必要がある機能と設定について説明します。 このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。 詳細な手順については、「 <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> 展開ガイドの展開ガイド」を参照してください。



</div>

**Lync Server 2013 パイロットプールを展開するには**

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  [ **Lync Server 2013** **Enterprise Edition フロントエンドプール**] に到達するまでツリーを展開します。

3.  [**Enterprise Edition フロントエンド プール**] を右クリックし、[**新しいフロントエンド プール**] を選択します。
    
    ![トポロジビルダーのサーバープールの選択サブメニュー](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "トポロジビルダーのサーバープールの選択サブメニュー")

4.  プールの FQDN を入力します。 パイロットプールを定義するときは、Enterprise Edition フロントエンドプールまたは Standard Edition サーバーを展開することを選択できます。 Lync Server 2013 では、パイロットプールの機能が従来のプールに展開されたものと一致している必要はありません。
    
    <div>
    

    > [!WARNING]  
    > パイロット プールに対して定義するプールまたはサーバーの完全修飾ドメイン名 (FQDN) は一意である必要があります。 現在展開されている Lync Server 2010 プールの名前、または現在展開されている他のすべてのサーバーの名前と一致させることはできません。

    
    </div>
    
    ![新しいフロントエンドプールの定義ウィザード FQDN ページ](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "新しいフロントエンドプールの定義ウィザード FQDN ページ")

5.  **[機能の選択]** ページで、このフロント エンド プールで必要な機能のチェック ボックスをオンにします。 たとえば、インスタントメッセージング (IM) とプレゼンス機能のみを展開する場合は、[会議] チェックボックスをオンにしてマルチパーティ IM を許可しますが、ダイヤルイン (PSTN) 会議、エンタープライズ Voip、または通話受付管理の各チェックボックスは、音声、ビデオ、および共同作業の会議機能を表すものであるため、選択しません。 機能の選択の詳細については、「展開」のドキュメントの「 [Define and configure a Front End pool Or Standard Edition server In Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 」を参照してください。
    
    ![フロントエンドプールの [機能の選択] ページ](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "フロントエンドプールの [機能の選択] ページ")

6.  [併置された **サーバーの役割の選択** ] ページで、仲介サーバーを Lync server 2013 に併置することをお勧めします。 従来のトポロジを Lync Server 2013 とマージする場合は、最初に Lync Server 2010 仲介サーバーを併置する必要があります。 トポロジをマージし、Lync Server 2013 仲介サーバーを構成した後で、展開プロセスで仲介サーバーの役割を Lync Server 2013 に移動するときに、併置された仲介サーバーを保持するか、スタンドアロンサーバーに変更するかを決定できます。
    
    ![フロントエンドプール [併置されたサーバーの役割の選択] ページ](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "フロントエンドプール [併置されたサーバーの役割の選択] ページ")

7.  パイロット プールの展開時は、[**サーバーの役割とこのフロントエンド プールの関連付け**] ページで、[**このフロントエンド プールのメディア コンポーネントで使用されるエッジ プールを有効にする**] オプションを選択しないでください。これは、移行のフェーズが進んだ段階で有効にしてオンラインにする機能です。現時点ではこの設定はオフのままにしてください。
    
    ![サーバーの役割をフロントエンドプールページと関連付ける](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "サーバーの役割をフロントエンドプールページと関連付ける")

8.  [**Office Web Apps Server の選択**] ページで [**新規作成**] をクリックし、アプリケーション サーバーの FQDN を指定します。
    
    ![新しい Office Web Apps サーバーの FQDN プロパティを定義する](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "新しい Office Web Apps サーバーの FQDN プロパティを定義する")

9.  [ **アーカイブ Sql server ストアの定義** ] ページで、lync Server のアーカイブと監視の両方のために sql server ストアを定義するときに、以前に lync server 2013 用に作成した sql server インスタンスを選択します。
    
    ![アーカイブ SQL Server ストアの定義ページ](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "アーカイブ SQL Server ストアの定義ページ")

10. トポロジを公開するために、[**Lync Server**] ノードを右クリックし、[**トポロジの公開**] をクリックします。
    
    ![トポロジビルダー構成済みトポロジを表示する](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "トポロジビルダー構成済みトポロジを表示する")

11. 公開プロセスが完了したら、[**完了**] をクリックします。

構成ストアのローカルコピーをインストールし、必要なサービスを開始するには、「展開」のドキュメントの「 [Setting Up Front End Servers And Front end プール For Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) 」を参照してください。


</div>

<span> </span>

</div>

</div>

</div>

