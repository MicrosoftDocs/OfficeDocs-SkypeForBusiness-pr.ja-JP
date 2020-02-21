---
title: 'Lync Server 2013: 会議の要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19f70df743e03494c0c54e180e2f23f960a752a1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 での会議の要件の定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-30_

どの会議機能を展開するかを決定するときには、ユーザーに提供したい機能とネットワーク帯域幅の能力を考慮する必要があります。次に示す質問の一覧では、組織の要件に基づいて展開する必要のある会議機能を決定するための会議計画プロセスを辿ります。

  - **ドキュメントのコラボレーションやアプリケーション共有を含む Web 会議を有効にしますか。**
    
    その場合は、Microsoft Lync Server 2013、計画ツール、またはトポロジビルダーでフロントエンドプール用の会議を有効にする必要があります。 会議を有効にすると、Web 会議と音声ビデオ会議の両方が有効になります。
    
    アプリケーション共有では、ドキュメントのコラボレーションよりも多くのネットワーク帯域幅を使用する必要があります。 Lync Server 2013 には、各アプリケーション共有セッションを制御するための調整メカニズムが用意されています。 既定では、セッションあたり 1.5 KB/秒に設定されます。
    
    アプリケーション共有は有効にせず、ドキュメントのコラボレーションを有効にする場合は、会議を有効にし、会議ポリシーを使用してアプリケーション共有を無効にすることができます。 会議ポリシーの構成の詳細については、「 [Lync Server 2013 の会議ポリシー](lync-server-2013-conferencing-policies.md)」を参照してください。
    
    ユーザーが PowerPoint プレゼンテーションを共有できるようにするには、Office Web Apps サーバーを構成する必要があります。 Office Web Apps サーバーの構成の詳細については、「 [Office Web Apps server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

  - **音声ビデオ会議を有効にしますか。**
    
    その場合は、Lync Server 2013、計画ツール、またはトポロジビルダーで、フロントエンドプール用の会議を有効にする必要があります。 会議を有効にすると、Web 会議と音声ビデオ会議の両方が有効になります。
    
    音声ビデオ会議では、Web 会議 (ドキュメントのコラボレーションやアプリケーション共有を含む) よりも多くのネットワーク帯域幅を使用する必要があります。音声ビデオ会議は有効にせず、Web 会議を有効にする場合は、会議を有効にし、会議ポリシーを使用して音声ビデオ会議を無効にすることができます。
    
    電話会議を有効にして、ビデオ会議は無効にする場合は、音声ビデオ会議を有効にし、会議ポリシーを使用してビデオ会議を使用できないようにすることができます。 あるいは、音声ビデオ会議を有効にして、特定のユーザーだけが音声ビデオ会議を開始または音声ビデオ会議に参加できるようにすることが可能です。
    
    <div>
    

    > [!NOTE]  
    > 音声ビデオ会議を使用するためにエンタープライズ Voip は必要ありません。 音声ビデオ会議を有効にすると、電話ソリューション用に PBX を使用していても、ユーザーはオーディオ デバイスがあればオーディオを会議に追加できます。

    
    </div>

  - **PSTN 電話を使用している場合、ユーザーが会議のオーディオ部分に参加できるようにしますか。**
    
    その場合は、ダイヤルイン会議を展開して有効にする必要があります。 組織内と外部の両方の招待ユーザーが、PSTN 電話を使用して会議のオーディオ部分に参加できるようになります。

  - **Lync Server 2013 クライアントを使用している外部ユーザーが、有効にした会議の種類に参加できるようにしますか。**
    
    その場合は、エッジ サーバーを展開します。 会議への外部参加を許可することで、Lync Server 2013 への投資を最大限に活用できます。 たとえば、Lync Server 2013 を使用しているラップトップを使用しているユーザーは、自宅、空港、お客様のサイトなどのどこからでも会議に参加できます。
    
    また、エッジ サーバーを展開していれば、顧客やベンダーなどの他の組織とフェデレーション関係を築くことができ、これらの組織のユーザーは、こちらのユーザーとより容易に共同作業を行うことができます。
    
    エッジサーバーの展開の詳細については、「 [lync server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」および「 [lync server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。 Office Web Apps サーバーの外部アクセスを有効にする方法の詳細については、「 [Office Web Apps サーバーを、リバースプロキシサーバーを使用して Lync server 2013 で公開](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)する」を参照してください。

  - **Lync Server 2013 会議に参加できるクライアントを制御しますか。**
    
    その場合は、サポートするクライアントオプションのみが利用できるように、会議参加ページを構成する必要があります。 ユーザーがスケジュールされた会議に参加するためのリンクをクリックするたびに、Lync Server 2013 はクライアントがコンピューターに既にインストールされているかどうかを検出します。 次に、既定のクライアントを起動し、代替クライアントへのリンクが含まれている [ミーティング参加] ページを開きます。 会議参加ページには、Microsoft Lync Web App を使用するオプションが常に表示されます。 このオプションに加えて、Communicator の出席者と以前のバージョンのリンクを含めるかどうかを決定できます。 詳細については、「 [Lync Server 2013 での会議参加ページの構成](lync-server-2013-configuring-the-meeting-join-page.md)」を参照してください。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での Web 会議の要件](lync-server-2013-web-conferencing-requirements.md)

  - [Lync Server 2013 での音声ビデオ会議の要件](lync-server-2013-a-v-conferencing-requirements.md)

  - [Lync Server 2013 でのダイヤルイン会議の要件](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での会議の計画](lync-server-2013-planning-for-conferencing.md)  
[Lync Server 2013 での会議の展開チェックリスト](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

