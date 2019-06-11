---
title: Lync Server 2013 パイロットプールの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93fb3c5062cc1f817d3de7b869f57600178ad454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>Lync Server 2013 パイロットプールの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-22_

Lync Server 2013 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。 パイロットプールでは、lync server 2013 と Lync Server 2010 の展開を共存させることができます。 [共存] は、すべてのユーザーとプールを Lync Server 2013 に移動するまで継続して使用できます。

パイロットプールを展開する場合は、[新しいフロントエンドプールの定義] ウィザードを使います。 Lync server 2010 プールにある Lync Server 2013 パイロットプールでも、同じ機能と作業負荷を展開する必要があります。 Lync Server 2010 環境をアーカイブまたは監視するためにアーカイブサーバー、監視サーバー、または System Center Operations Manager を展開していて、移行を通じてアーカイブまたは監視を継続する必要がある場合は、次のものも展開する必要があります。パイロット環境の機能。 Lync Server 2010 環境をアーカイブまたは監視するために展開したバージョンでは、Lync Server 2013 環境のデータはキャプチャされません。

<div>


> [!NOTE]  
> 次の手順では、パイロットプールの全体的な展開プロセスの一部として考慮する必要がある機能と設定について説明します。 このセクションでは、パイロットプールの展開の一部として考慮する必要がある重要なポイントについて説明します。 詳細な手順については、「 <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A>展開ガイド」を参照してください。



</div>

**Lync Server 2013 パイロットプールを展開するには**

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  **Lync Server 2013** **Enterprise Edition のフロントエンドプール**に到達するまでツリーを展開します。

3.  [ **Enterprise Edition のフロントエンドプール**] を右クリックし、[**新しいフロントエンドプール**] を選択します。
    
    ![トポロジビルダーサーバープールの選択サブメニュー](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "トポロジビルダーサーバープールの選択サブメニュー")

4.  プールの FQDN を入力します。 パイロットプールを定義する場合は、Enterprise Edition のフロントエンドプールまたは Standard Edition サーバーを展開することを選択できます。 Lync Server 2013 では、パイロットプールの機能が、従来のプールに展開されたものと一致する必要はありません。
    
    <div>
    

    > [!WARNING]  
    > パイロットプールに対して定義するプールまたはサーバーの完全修飾ドメイン名 (FQDN) は一意である必要があります。 現在展開されている Lync Server 2010 プールの名前、または現在展開されている他のサーバーの名前と一致させることはできません。

    
    </div>
    
    ![新しいフロントエンドプールウィザードの FQDN ページを定義]する(images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "新しいフロントエンドプールウィザードの FQDN ページを定義")する

5.  **[機能の選択**] ページで、このフロントエンドプールに必要な機能のチェックボックスをオンにします。 たとえば、インスタントメッセージング (IM) とプレゼンス機能のみを展開している場合、[会議] チェックボックスをオンにして、マルチパーティ IM を許可しますが、ダイヤルイン (PSTN) 会議、エンタープライズボイス、または通話受付制御のチェックボックスは選択しません。音声、ビデオ、および共同作業の会議機能を表します。 機能の選択の詳細については、展開ドキュメントの「 [Lync server 2013 でのフロントエンドプールまたは Standard Edition サーバーの定義と構成](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)」を参照してください。
    
    ![フロントエンドプールの [機能] ページ](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "フロントエンドプールの [機能] ページ")

6.  **[併置**されたサーバーの役割の選択] ページで、Lync server 2013 で仲介サーバーを検索することをお勧めします。 従来のトポロジを Lync Server 2013 と統合する場合は、最初に Lync Server 2010 仲介サーバーを検索する必要があります。 トポロジをマージして Lync Server 2013 仲介サーバーを構成した後、展開後に仲介サーバーの役割を Lync Server 2013 に移行するときに、併置された仲介サーバーを保持するか、スタンドアロンサーバーに変更するかを決定できます。プロセス.
    
    ![フロントエンドプール [併置したサーバーの役割] ページを選択]する(images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "フロントエンドプール [併置したサーバーの役割] ページを選択")する

7.  パイロットプールの展開中に、[**サーバーの役割をこのフロントエンドプールに関連付ける**] ページで、[**このフロントエンドプールのメディアコンポーネントで使用するエッジプールを有効**にする] オプションを選択しないでください。 これは、移行の後のフェーズで有効にしてオンラインにする機能です。 ここでは、この設定をオフのままにしておきます。
    
    ![サーバーの役割をフロントエンドプールページに関連付ける](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "サーバーの役割をフロントエンドプールページに関連付ける")

8.  [ **Office Web Apps サーバーを選択**してください] ページで、[**新規**] をクリックし、アプリケーションサーバーの FQDN を指定します。
    
    ![新しい Office Web Apps サーバーの FQDN プロパティを定義]する(images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "新しい Office Web Apps サーバーの FQDN プロパティを定義")する

9.  Lync Server のアーカイブと監視の両方に対して SQL Server ストアを定義する場合は、[**アーカイブ SQL Server ストアの定義**] ページで、以前に lync server 2013 用に作成した sql server インスタンスを選びます。
    
    ![アーカイブ SQL Server ストアの定義ページ](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "アーカイブ SQL Server ストアの定義ページ")

10. トポロジを公開するには、[ **Lync Server** ] ノードを右クリックし、[**トポロジの公開**] をクリックします。
    
    ![構成済みトポロジが表示されたトポロジビルダー](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "構成済みトポロジが表示されたトポロジビルダー")

11. 発行プロセスが完了したら、[**完了**] をクリックします。

構成ストアのローカルコピーをインストールし、必要なサービスを開始するには、「展開ドキュメントで[Lync Server 2013 用のフロントエンドサーバーとフロントエンドプールを設定](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)する」を参照してください。


</div>

<span> </span>

</div>

</div>

</div>

