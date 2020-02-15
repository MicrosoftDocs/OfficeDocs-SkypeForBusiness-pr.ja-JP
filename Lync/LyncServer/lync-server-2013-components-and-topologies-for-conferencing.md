---
title: Lync Server 2013 の会議のコンポーネントとトポロジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d14c12ad1e28dc2a40fed5b19b5928a5bedc069
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 の会議のコンポーネントとトポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-04_

トポロジビルダーで [会議] を選択すると、電話会議はフロントエンドサーバーまたは Standard Edition サーバーの一部として展開されます。 ダイヤルイン会議と PowerPoint 共有には、追加コンポーネントと構成が必要です。 このセクションでは、Web 会議、音声ビデオ会議、およびダイヤルイン会議でサポートされるコンポーネントとトポロジについて説明します。

<div>

## <a name="supported-components"></a>サポートされるコンポーネント

Web 会議と音声ビデオ会議のみが必要なコンポーネントは、組織のフロントエンドサーバーまたは Standard Edition サーバーです。 フロントエンドサーバーおよび Standard Edition サーバーのハードウェアおよびソフトウェア要件の一覧については、「lync server [2013 の場合はサポートされるハードウェア](lync-server-2013-supported-hardware.md)」および「 [lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート](lync-server-2013-server-software-and-infrastructure-support.md)」を参照してください。

Lync Server 2013 は、Office Web Apps および Office Web Apps サーバーを使用して、PowerPoint プレゼンテーションの共有とレンダリングを処理します。 Office Web Apps サーバーのインストールと構成の詳細については、「 [Office Web Apps server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

Web 会議および音声ビデオ会議の要件に加えて、ダイヤルイン会議は次の Lync Server 2013 コンポーネントを使用します。

  - **Application service**   アプリケーションサービスは、統合コミュニケーション (UC) アプリケーションを展開、ホスト、および管理するためのプラットフォームを提供します。 ダイヤルイン会議では、アプリケーションサービスを必要とする2つの UC アプリケーション (会議アテンダントと会議アナウンス) を使用します。 アプリケーション サービスは、会議ワークロードを展開してダイヤルイン会議オプションを選択した場合に、既定でフロント エンド プール内のすべてのフロント エンド サーバーおよびすべての Standard Edition サーバーにインストールされてアクティブ化されます。

  - **電話会議アテンダント**   アプリケーション会議アテンダントアプリケーションは、公衆交換電話網 (PSTN) 通話を受け付け、プロンプトを再生して、音声ビデオ会議への通話を参加させる統合コミュニケーションアプリケーションです。 会議ワークロードを展開し、[ダイヤルイン会議] オプションを選択すると、既定で会議アテンダントアプリケーションがインストールされ、アクティブ化されます。

  - **会議アナウンスアプリケーション**   会議アナウンスアプリケーションは、参加者が会議に参加または退室したとき、参加者がミュートまたはミュート解除、会議ロビーに入ったとき、または会議がロックまたはロック解除されたときなど、特定のアクションについてトーンと音声を再生する統合コミュニケーションアプリケーションです。 会議アナウンスアプリケーションは、電話のキーパッドからのデュアルトーン多重周波数 (DTMF) コマンドもサポートします。 会議ワークロードを展開し、[ダイヤルイン会議] オプションを選択すると、既定で会議アナウンスアプリケーションが自動的にインストールされ、アクティブ化されます。

  - **[ダイヤルイン会議の設定] ページ**   [ダイヤルイン会議の設定] ページには、使用可能な言語が含まれている会議のダイヤルイン番号、割り当てられている会議情報 (スケジュールする必要がない会議の場合)、会議中の DTMF コントロール、および個人識別番号 (PIN) と割り当てられた会議情報の管理をサポートします。 [ダイヤルイン会議の設定] ページは、Web サービスの一部として自動的にインストールされます。

  - **Lync server 2013、仲介サーバーおよび pstn ゲートウェイ**   のダイヤルイン会議では、仲介サーバーと pstn ゲートウェイの2013間で信号 (およびメディア、一部の構成) を変換する必要があります。また、pstn ゲートウェイは、仲介サーバーと pstn ゲートウェイ間の信号とメディアを変換します。 ダイヤルイン会議では、少なくとも 1 つの仲介サーバーと、少なくとも 1 つの次のものを展開する必要があります。
    
      - PSTN ゲートウェイ
    
      - IP-PBX
    
      - セッション ボーダー コントローラー (SBC) (SIP トランクを構成して接続するインターネット テレフォニー サービス プロバイダー (ITSP) のため)
    
    <div>
    

    > [!NOTE]  
    > エンタープライズ Voip を展開している場合、仲介サーバーと PSTN ゲートウェイはエンタープライズ Voip 展開に含まれています。 エンタープライズ VoIP を展開していない場合、ダイヤルイン会議用に、少なくとも 1 つの仲介サーバー、および少なくとも 1 つの PSTN ゲートウェイ、IP-PBX、または SBC を展開する必要があります。

    
    </div>

  - **ファイルストア**   ファイルストアは、記録された名前のオーディオファイルに使用されます。 ファイル ストアは、すべての Enterprise Edition 展開または Standard Edition 展開の標準コンポーネントです。

  - **ユーザーストア**   のユーザーストアは、ユーザーの Lync Server 2013 pin を格納するために使用されます。 PIN はハッシュされます。 ユーザー ストアは、すべての Enterprise Edition 展開または Standard Edition 展開の標準コンポーネントです。

  - **Lync server コントロールパネル**   lync server コントロールパネルを使用して、いくつかのダイヤルイン設定を構成できます。

  - **Lync server 管理**   シェル lync server 管理シェルコマンドレットを使用して、すべてのダイヤルイン設定を構成できます。 Lync Server 管理シェルコマンドレットは、会議アテンダントアプリケーションおよび会議アナウンスアプリケーションの展開、構成、実行、監視、およびトラブルシューティングに使用できます。 特定のコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。

</div>

<div>

## <a name="supported-topologies"></a>サポートされるトポロジ

Lync Server 2013 では、会議サービスを実行しているサーバーは、常にフロントエンドサーバーまたは Standard Edition サーバーと併置されています。 初期展開時に、トポロジビルダーでは、トポロジに電話会議を含めるオプションが提供されます。 トポロジー ビルダーを使用して、既存の展開に会議を追加することもできます。 詳細については、「 [Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。

<div>

## <a name="dial-in-conferencing-toplogies"></a>ダイヤルイン会議のトポロジ

次のトポロジと構成にダイヤルイン会議を展開できます。

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - エンタープライズ Voip の有無にかかわらず

アプリケーションサービス、会議アテンダントアプリケーション、および会議アナウンスアプリケーションは、中央サイトに展開できますが、ブランチサイトに展開することはできません。

<div>


> [!NOTE]  
> ダイヤルイン会議を展開する場合は、Lync Server 2013 会議を展開するすべてのプールに展開する必要があります。 プールごとにアクセス番号を割り当てる必要はありませんが、プールごとにダイヤルイン会議機能を展開する必要があります。 この要件では、ユーザーが1つのプールのアクセス番号を呼び出して Lync Server 2013 会議を別のプールに参加させるときに、記録された名前の機能がサポートされます。



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Lync Server 2013 および Office Web Apps でサポートされているトポロジ

Lync Server 2013 には、Office Web Apps サーバーを構成するための次のような方法が用意されています。 必要に応じて次のことができます。

  - **組織のファイアウォールの背後にある Lync Server 2013 と Office Web Apps サーバーの両方を、同じネットワークゾーンにインストールします。** このトポロジでは、Office Web Apps サーバーへの外部アクセスはリバースプロキシサーバー経由で提供されます。 Lync Server 2013 と Office Web Apps サーバー (または Office Web Apps サーバーファーム) は、オンプレミスと組織のファイアウォールの背後にインストールされています。 できれば、Lync Server と同じネットワークゾーンに Office Web Apps サーバーをインストールすることをお勧めします。
    
    外部の Lync クライアントは、リバースプロキシサーバーを使用して Lync Server 2013 および Office Web Apps サーバーに接続できます。これは、インターネットからの要求を受けて内部ネットワークに転送されるサーバーです。 (内部クライアントは、Office Web Apps サーバーに直接接続できるため、リバースプロキシサーバーを使用する必要はありません)。このトポロジは、Lync Server 2013 のみで使用される専用の Office Web Apps サーバーファームを使用する場合に最適に機能します。

  - **外部に展開された Office Web Apps サーバーの使用**
    
    このトポロジでは、Lync Server 2013 がオンプレミスで展開され、Lync Server ネットワークゾーンの外側に展開された Office Web Apps サーバーを使用します。 これは、Office Web Apps サーバーが企業内の複数のアプリケーション間で共有されており、Lync Server が Office Web Apps サーバーの外部インターフェイスを使用する必要があるネットワークに展開される場合に発生する可能性があります。
    
    リバースプロキシサーバーをインストールする必要はありません。その代わりに、Office Web Apps サーバーから Lync Server 2013 へのすべての要求が、エッジサーバーを経由してルーティングされます。 内部と外部の両方の Lync クライアントは、外部 URL を使用して Office Web Apps サーバーに接続します。
    
    Office Web Apps サーバーが内部ファイアウォールの外側に展開されている場合は、[トポロジビルダー] の [ **Office Web Apps サーバーは外部ネットワークで展開されています (つまり、境界またはインターネット)** ] オプションを選択します。 詳細については[、「Office Web Apps Server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

選択するトポロジにかかわらず、ファイアウォールの正しいポートを開くことは重要です。 Office Web Apps サーバー、ロードバランサー、または Lync Server のファイアウォールによって、DNS 名、IP アドレス、およびポートがブロックされないようにする必要があります。

<div>


> [!NOTE]  
> Office Web Apps サーバーへの外部アクセスを提供するもう1つの方法は、境界ネットワークにサーバーを展開することです。 これを行う場合は、Office Web Apps サーバーのセットアップでは、サーバーコンピューターが Active Directory ドメインのメンバーである必要があることに注意してください。 ネットワークポリシーによって、境界ネットワーク内のコンピューターが Active Directory ドメインのメンバーになることが許可されていない場合は、境界ネットワークに Office Web Apps サーバーをインストールしないことをお勧めします。 その代わりに、Office Web Apps サーバーを内部ネットワークにインストールし、リバースプロキシサーバー経由で外部ユーザーアクセスを提供する必要があります。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

