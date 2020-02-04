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
ms.openlocfilehash: c19269ef06fc2aa7ec19e2ede53f406b345536b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 での会議の要件の定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-30_

どの会議機能を展開するかを決定するときには、ユーザーに提供したい機能とネットワーク帯域幅の能力を考慮する必要があります。 次の質問リストは、組織の要件に基づいて、会議の計画プロセスを通じて、展開する必要がある会議の機能を決定する方法を示しています。

  - **ドキュメントのコラボレーションやアプリケーション共有を含む Web 会議を有効にしますか。**
    
    その場合は、Microsoft Lync Server 2013、計画ツール、またはトポロジビルダーで、フロントエンドプールに対して会議を有効にする必要があります。 会議を有効にすると、web 会議と A/V の両方の会議が有効になります。
    
    アプリケーション共有では、ドキュメントのコラボレーションよりも多くのネットワーク帯域幅を使用する必要があります。 Lync Server 2013 には、各アプリケーション共有セッションを制御するための調整メカニズムが用意されています。 既定では、セッションあたり 1.5 KB/秒に設定されます。
    
    アプリケーション共有を有効にし、ドキュメントの共同作業を行う場合は、会議を有効にして会議のポリシーを使用して、アプリケーションの共有を無効にすることができます。 会議ポリシーの構成の詳細については、「 [Lync Server 2013 の会議ポリシー](lync-server-2013-conferencing-policies.md)」を参照してください。
    
    ユーザーが PowerPoint プレゼンテーションを共有できるようにするには、Office Web Apps サーバーを構成する必要があります。 Office Web Apps サーバーの構成の詳細については、「 [Office Web Apps server および Lync server 2013 との統合を構成する](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

  - **A/V 会議を有効にしますか?**
    
    その場合は、Lync Server 2013、計画ツール、またはトポロジビルダーで、フロントエンドプールに対して会議を有効にする必要があります。 会議を有効にすると、web 会議と A/V の両方の会議が有効になります。
    
    A/V 会議には、web 会議 (ドキュメントのグループ作業とアプリケーションの共有など) よりも多くのネットワーク帯域幅が必要です。 電話会議を有効にしても、web 会議を有効にしたい場合は、会議を有効にして、会議ポリシーを使って、A/V 会議を無効にすることができます。
    
    音声会議を有効にするが、ビデオ会議を有効にしない場合は、A/V 会議を有効にして、会議ポリシーを使ってビデオ会議を防ぐことができます。 あるいは、音声ビデオ会議を有効にして、特定のユーザーだけが音声ビデオ会議を開始または音声ビデオ会議に参加できるようにすることが可能です。
    
    <div>
    

    > [!NOTE]  
    > 音声ビデオ会議を使用するためにエンタープライズ VoIP は必要ありません。音声ビデオ会議を有効にすると、電話ソリューション用に PBX を使用していても、ユーザーはオーディオ デバイスがあればオーディオを会議に追加できます。

    
    </div>

  - **PSTN 携帯電話を使用しているときに、ユーザーが会議のオーディオ部分に参加できるようにしますか?**
    
    その場合は、ダイヤルイン会議を展開して有効にする必要があります。組織内と外部の両方の招待ユーザーが、PSTN 電話を使用して会議のオーディオ部分に参加できるようになります。

  - **Lync Server 2013 クライアントでの外部ユーザーが、有効にした会議の種類に参加できるようにしますか?**
    
    その場合は、エッジサーバーを展開する必要があります。 会議に外部の参加を許可することで、Lync Server 2013 で投資を最大限に活用できます。 たとえば、Lync Server 2013 を使っているノート pc のユーザーは、自宅、空港、顧客サイトなど、どこからでも会議に参加できます。
    
    さらに、エッジサーバーが展開されていると、顧客やベンダーなどの他の組織とのフェデレーション関係を作成することができます。また、これらの組織のユーザーは、ユーザーとの共同作業を簡単に行うことができます。
    
    エッジサーバーの展開の詳細については、「 [Lync server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」および「 [lync server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。 Office Web Apps サーバーの外部アクセスを有効にする方法について詳しくは、「[リバースプロキシサーバーを使用して Lync server 2013 で Office Web Apps サーバーを発行](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)する」をご覧ください。

  - **Lync Server 2013 会議に参加できるクライアントを制御しますか?**
    
    その場合は、会議の参加ページを構成して、サポートするクライアントオプションのみが利用できるようにする必要があります。 スケジュールされた会議に参加するためにユーザーがリンクをクリックするたびに、Lync Server 2013 はクライアントがコンピューターに既にインストールされているかどうかを検出します。 次に、既定のクライアントが起動され、[会議参加] ページが開きます。このページには、代替クライアントへのリンクが含まれています。 [会議参加] ページには、常に Microsoft Lync Web App を使用するオプションが表示されます。 このオプションに加えて、出席者と以前のバージョンの Communicator のリンクを含めるかどうかを決定できます。 詳細については、「 [Lync Server 2013 で会議の参加ページを構成する](lync-server-2013-configuring-the-meeting-join-page.md)」を参照してください。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での Web 会議の要件](lync-server-2013-web-conferencing-requirements.md)

  - [Lync Server 2013 での A/V 会議の要件](lync-server-2013-a-v-conferencing-requirements.md)

  - [Lync Server 2013 でのダイヤルイン会議の要件](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での会議の計画](lync-server-2013-planning-for-conferencing.md)  
[Lync Server 2013 の会議の展開チェックリスト](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

