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
ms.openlocfilehash: 46e6d4bd34c20038e430323b0f78ccf4f918aa62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724047"
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

Lync Server 2013 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。 パイロットプールは、Lync Server 2013 と Office Communications Server 2007 R2 の展開との共存をテストする場所です。 [共存] は、すべてのユーザーとプールを Lync Server 2013 に移動するまで継続して使用できます。

パイロットプールを展開する場合は、[新しいフロントエンドプールの定義] ウィザードを使います。 Lync Server 2013 パイロットプールで、Office Communications Server 2007 R2 プールにあるものと同じ機能とワークロードを展開する必要があります。 Office Communications Server 2007 R2 環境をアーカイブまたは監視するためにアーカイブサーバー、監視サーバー、または System Center Operations Manager を展開していて、移行を通じてアーカイブまたは監視を継続する場合は、パイロット環境でも、これらの機能が展開されます。 Office Communications Server 2007 R2 環境をアーカイブまたは監視するために展開したバージョンでは、Lync Server 2013 環境のデータはキャプチャされません。

<div>


> [!NOTE]  
> 次の手順では、パイロットプールの全体的な展開プロセスの一部として考慮する必要がある機能と設定について説明します。 このセクションでは、パイロットプールの展開の一部として考慮する必要がある重要なポイントについて説明します。 詳細な手順については、「 <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A>展開ガイド」を参照してください。



</div>

**Lync Server 2013 パイロットプールを展開するには**

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジビルダーを開き、新しいトポロジの作成を選択します。

3.  プライマリ SIP ドメインを入力します。
    
    ![新しいトポロジを作成し、プライマリドメインページを定義する](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "新しいトポロジを作成し、プライマリドメインページを定義する")

4.  [**新しいフロントエンドプールの定義**] ウィザードが表示されるまで、ウィザードの手順を続行します。 [ 次へ] をクリックします。

5.  プールの FQDN を入力します。 パイロットプールを定義する場合は、Enterprise Edition のフロントエンドプールまたは Standard Edition サーバーを展開することを選択できます。 Lync Server 2013 では、パイロットプールの機能が、従来のプールに展開されたものと一致する必要はありません。
    
    <div>
    

    > [!WARNING]  
    > パイロットプールに対して定義するプールまたはサーバーの完全修飾ドメイン名 (FQDN) は一意である必要があります。 現在展開されている Office Communications Server 2007 R2 プール、または現在展開されているその他のサーバーの名前と一致させることはできません。

    
    </div>
    
    ![フロントエンドプールの FQDN ページを定義する](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "フロントエンドプールの FQDN ページを定義する")

6.  プールに追加されるコンピューターを定義します。
    
    ![[新しいフロントエンドプールの定義] ダイアログ](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "[新しいフロントエンドプールの定義] ダイアログ")

7.  **[機能の選択**] ページで、このフロントエンドプールに必要な機能のチェックボックスをオンにします。 たとえば、インスタントメッセージング (IM) とプレゼンス機能のみを展開している場合、[会議] チェックボックスをオンにして、マルチパーティ IM を許可しますが、ダイヤルイン (PSTN) 会議、エンタープライズボイス、または通話受付制御のチェックボックスは選択しません。音声、ビデオ、および共同作業の会議機能を表します。 機能の選択の詳細については、展開ドキュメントの「 [Lync server 2013 でのフロントエンドプールまたは Standard Edition サーバーの定義と構成](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)」を参照してください。
    
    ![フロントエンドプールの [機能] ページ](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "フロントエンドプールの [機能] ページ")

8.  **[併置**されたサーバーの役割の選択] ページで、Lync server 2013 で仲介サーバーを検索することをお勧めします。 従来のトポロジを Lync Server 2013 と統合する場合は、最初に Office Communications Server 2007 R2 仲介サーバーを検索する必要があります。 トポロジをマージして Lync Server 2013 仲介サーバーを構成した後、展開後に仲介サーバーの役割を Lync Server 2013 に移行するときに、併置された仲介サーバーを保持するか、スタンドアロンサーバーに変更するかを決定できます。プロセス.
    
    ![フロントエンドプール [併置したサーバーの役割] ページを選択する](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "フロントエンドプール [併置したサーバーの役割] ページを選択する")

9.  パイロットプールの展開中に、[**サーバーの役割をこのフロントエンドプールに関連付ける**] ページで、[**このフロントエンドプールのメディアコンポーネントで使用するエッジプールを有効**にする] オプションを選択しないでください。 これは、移行の後のフェーズで有効にしてオンラインにする機能です。 ここでは、この設定をオフのままにしておきます。
    
    ![サーバーの役割をフロントエンドプールページに関連付ける](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "サーバーの役割をフロントエンドプールページに関連付ける")

10. [ **Office Web Apps サーバーを選択**してください] ページで、[**新規**] をクリックし、アプリケーションサーバーの FQDN を指定します。
    
    ![新しい Office Web Apps サーバーの FQDN プロパティを定義する](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "新しい Office Web Apps サーバーの FQDN プロパティを定義する")

11. [**アーカイブ SQL Server ストアの定義**] ページで、以前に Lync Server 2013 用に作成した SQL server インスタンスを選びます。
    
    ![アーカイブ SQL Server ストアの定義ページ](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "アーカイブ SQL Server ストアの定義ページ")

12. [ **MONITORING SQL server ストアの定義**] ページで、以前に Lync Server 2013 用に作成した sql server インスタンスを選びます。 [**完了**] をクリックします。

13. トポロジビルダーのトップノードで、[ **Lync Server** ] を右クリックし、[プロパティの編集] をクリックし**ます。** [ **Simple url**] をクリックします。

14. **管理アクセスの URL**を更新します。
    
    ![[プロパティの編集] の [シンプルな Url] ページ](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "[プロパティの編集] の [シンプルな Url] ページ")
    
    単純な Url の詳細については、展開ドキュメントの「 [Lync Server 2013 での単純な url の編集または構成](lync-server-2013-edit-or-configure-simple-urls.md)」を参照してください。

15. [**プロパティの編集**] の [**サーバーの管理**] をクリックします。

16. ドロップダウンリストから、Lync Server 2013 プールを選択します。
    
    ![[プロパティの中央管理] ページを編集する](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "[プロパティの中央管理] ページを編集する")

17. [OK] をクリックし**て、[プロパティの編集**] ページを閉じます。

18. [**操作**] メニューの [**トポロジの公開**] を選びます。

19. 発行プロセスが完了したら、[**完了**] をクリックします。

20. Lync Server 2013 展開ウィザードに戻り、[ **Lync Server System のインストールまたは更新**] をクリックします。
    
    ![Lync Server 2013 展開ウィザード](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 展開ウィザード")

構成ストアのローカルコピーをインストールし、必要なサービスを開始するには、「展開ドキュメントで[Lync Server 2013 用のフロントエンドサーバーとフロントエンドプールを設定](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)する」を参照してください。


</div>

<span> </span>

</div>

</div>

</div>

