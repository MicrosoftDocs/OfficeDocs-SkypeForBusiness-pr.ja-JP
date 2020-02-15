---
title: Lync Server 2013 パイロットプールの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c97ea5304309aaf635ac284e792a73634c5ae19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>Lync Server 2013 パイロットプールの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-22_

Lync Server 2013 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。 パイロットプールは、Office Communications Server 2007 R2 展開と Lync Server 2013 の共存をテストする場所です。 共存は、すべてのユーザーとプールを Lync Server 2013 に移動するまで、一時的な状態になります。

パイロット プールを展開するときには、新しいフロントエンド プールの定義ウィザードを使用します。 Office Communications Server 2007 R2 プールにある Lync Server 2013 パイロットプールに、同じ機能とワークロードを展開する必要があります。 アーカイブサーバー、監視サーバー、または System Center Operations Manager を使用して Office Communications Server 2007 R2 環境のアーカイブまたは監視を行っていて、移行を通じてアーカイブまたは監視を続行する必要がある場合は、また、これらの機能をパイロット環境に展開します。 Office Communications Server 2007 R2 環境をアーカイブまたは監視するために展開したバージョンでは、Lync Server 2013 環境のデータはキャプチャされません。

<div>


> [!NOTE]  
> 次の手順では、パイロット プール全体の展開プロセスの中で検討する必要がある機能と設定について説明します。 このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。 詳細な手順については、「 <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A>展開ガイドの展開ガイド」を参照してください。



</div>

**Lync Server 2013 パイロットプールを展開するには**

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジ ビルダーを開き、トポロジの新規作成を選択します。

3.  プライマリ SIP ドメインを入力します。
    
    ![新しいトポロジの作成、プライマリドメインページの定義](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "新しいトポロジの作成、プライマリドメインページの定義")

4.  **新しいフロントエンド プールの定義**ウィザードに達するまで、ウィザードの入力を続けます。 [次へ] をクリックします。

5.  プールの FQDN を入力します。 パイロットプールを定義するときは、Enterprise Edition フロントエンドプールまたは Standard Edition サーバーを展開することを選択できます。 Lync Server 2013 では、パイロットプールの機能が従来のプールに展開されたものと一致している必要はありません。
    
    <div>
    

    > [!WARNING]  
    > パイロット プールに対して定義するプールまたはサーバーの完全修飾ドメイン名 (FQDN) は一意である必要があります。 現在展開されている Office Communications Server 2007 R2 プールの名前、または現在展開されている他のすべてのサーバーの名前と一致させることはできません。

    
    </div>
    
    ![フロントエンドプールの FQDN ページを定義する](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "フロントエンドプールの FQDN ページを定義する")

6.  プールに追加されるコンピューターを定義します。
    
    ![[新しいフロントエンドプールの定義] ダイアログ](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "[新しいフロントエンドプールの定義] ダイアログ")

7.  **[機能の選択]** ページで、このフロント エンド プールで必要な機能のチェック ボックスをオンにします。 たとえば、インスタントメッセージング (IM) とプレゼンス機能のみを展開する場合は、[会議] チェックボックスをオンにしてマルチパーティ IM を許可しますが、ダイヤルイン (PSTN) 会議、エンタープライズ Voip、または通話受付管理のチェックボックスは選択しません。音声、ビデオ、および共同作業の会議機能を表すからです。 機能の選択の詳細については、「展開」のドキュメントの「 [Define and configure a Front End pool Or Standard Edition server In Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 」を参照してください。
    
    ![フロントエンドプールの [機能の選択] ページ](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "フロントエンドプールの [機能の選択] ページ")

8.  [併置された**サーバーの役割の選択**] ページで、仲介サーバーを Lync server 2013 に併置することをお勧めします。 従来のトポロジを Lync Server 2013 とマージする場合は、最初に Office Communications Server 2007 R2 仲介サーバーを併置する必要があります。 トポロジをマージし、Lync Server 2013 仲介サーバーを構成した後で、仲介サーバーの役割を後で Lync Server 2013 に移動するときに、併置された仲介サーバーを保持するか、スタンドアロンサーバーに変更するかを決定できます。手順.
    
    ![フロントエンドプール [併置されたサーバーの役割の選択] ページ](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "フロントエンドプール [併置されたサーバーの役割の選択] ページ")

9.  パイロット プールの展開時は、[**サーバーの役割とこのフロントエンド プールの関連付け**] ページで、[**このフロントエンド プールのメディア コンポーネントで使用されるエッジ プールを有効にする**] オプションを選択しないでください。これは、移行のフェーズが進んだ段階で有効にしてオンラインにする機能です。現時点ではこの設定はオフのままにしてください。
    
    ![サーバーの役割をフロントエンドプールページと関連付ける](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "サーバーの役割をフロントエンドプールページと関連付ける")

10. [**Office Web Apps Server の選択**] ページで [**新規作成**] をクリックし、アプリケーション サーバーの FQDN を指定します。
    
    ![新しい Office Web Apps サーバーの FQDN プロパティを定義する](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "新しい Office Web Apps サーバーの FQDN プロパティを定義する")

11. [**アーカイブ SQL Server ストアの定義**] ページで、以前に Lync Server 2013 用に作成した sql server インスタンスを選択します。
    
    ![アーカイブ SQL Server ストアの定義ページ](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "アーカイブ SQL Server ストアの定義ページ")

12. [**監視 SQL server ストアの定義**] ページで、以前に Lync Server 2013 用に作成した sql server インスタンスを選択します。 [**完了**] をクリックします。

13. トポロジ ビルダーの最上位ノードで、[**Lync Server**] を右クリックし、[**プロパティの編集**] をクリックします。[**簡易 URL**] をクリックします。

14. [**管理アクセス URL**] を更新します。
    
    ![[プロパティの編集]、[簡易 Url] ページ](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "[プロパティの編集]、[簡易 Url] ページ")
    
    簡易 Url の詳細については、「展開」のドキュメントの「 [Edit or configure Simple urls In Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) 」を参照してください。

15. [**プロパティの編集**] で、[**中央管理サーバー**] をクリックします。

16. ドロップダウンリストから、[Lync Server 2013] プールを選択します。
    
    ![[プロパティの編集]、[中央管理サーバー] ページ](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "[プロパティの編集]、[中央管理サーバー] ページ")

17. [OK] をクリックして、[**プロパティの編集**] ページを閉じます。

18. [**アクション**] メニューの [**トポロジの公開**] を選択します。

19. 公開プロセスが完了したら、[**完了**] をクリックします。

20. Lync Server 2013 展開ウィザードに戻り、[ **Lync Server システムのインストールまたは更新**] をクリックします。
    
    ![Lync Server 2013 展開ウィザード](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 展開ウィザード")

構成ストアのローカルコピーをインストールし、必要なサービスを開始するには、「展開」のドキュメントの「 [Setting Up Front End Servers And Front end プール For Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) 」を参照してください。


</div>

<span> </span>

</div>

</div>

</div>

