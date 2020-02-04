---
title: 'Lync Server 2013: 会議のコンポーネントおよびトポロジ'
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
ms.openlocfilehash: db44e7c8430865fcf8138c9b51f6e700ff85dd7b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 の会議のコンポーネントおよびトポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-04_

[トポロジビルダー] で [会議] を選択すると、会議はフロントエンドサーバーまたは Standard Edition サーバーの一部として展開されます。 ダイヤルイン会議と PowerPoint 共有には、追加のコンポーネントと構成が必要です。 以下のセクションでは、web 会議、A/V 会議、ダイヤルイン会議でサポートされているコンポーネントとトポロジについて説明します。

<div>

## <a name="supported-components"></a>サポートされているコンポーネント

唯一のコンポーネント web 会議と A/V 会議が必要なのは、組織のフロントエンドサーバーまたは Standard Edition サーバーだけです。 フロントエンドサーバーおよび Standard Edition サーバーのハードウェアとソフトウェアの要件の一覧については、「[サポートされているハードウェアと lync 2013 server 2013 の](lync-server-2013-supported-hardware.md)[サーバーソフトウェアおよびサーバーソフトウェアとインフラストラクチャのサポート](lync-server-2013-server-software-and-infrastructure-support.md)」を参照してください。

Lync Server 2013 は、PowerPoint プレゼンテーションの共有とレンダリングを処理するために、Office Web Apps と Office Web Apps サーバーを使用します。 Office Web Apps サーバーのインストールと構成の詳細については、「 [Office Web Apps サーバーおよび Lync server 2013 との統合を構成する](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

ダイヤルイン会議では、web 会議と A/V 会議の要件に加えて、次の Lync Server 2013 コンポーネントを使用します。

  - **アプリケーションサービス**   アプリケーションサービスは、統合コミュニケーション (UC) アプリケーションを展開、ホスティング、および管理するためのプラットフォームを提供します。 [ダイヤルイン会議] では、アプリケーションサービスが必要な2つの UC アプリケーション (会議アテンダントと会議のお知らせ) を使用します。 アプリケーションサービスは、電話会議のワークロードを展開して、[ダイヤルイン会議] オプションを選択すると、フロントエンドプールのすべてのフロントエンドサーバーと、すべての Standard Edition サーバーで既定でインストールされ、有効になります。

  - **会議アテンダントアプリケーション**   会議の応答アプリケーションは、公衆交換電話網 (PSTN) 通話、プロンプトの再生、a/V 会議への通話の参加を行う、統合された通信アプリケーションです。 会議のワークロードを展開して、[ダイヤルイン会議] オプションを選択すると、会議アテンダントアプリケーションが既定でインストールされ、有効になります。

  - **会議のお知らせアプリケーション**   会議のお知らせアプリケーションは、参加者が会議に参加したり退出したりするとき、参加者がミュートまたはミュートしたとき、参加者が会議ロビーに入ったとき、または会議がロックまたはロック解除されているときなど、特定の操作に対して PSTN の参加者に対してトーンを再生する統合通信アプリケーションです。 会議アナウンスメントアプリケーションでは、電話のキーパッドからのデュアルトーンマルチ周波数 (DTMF) コマンドもサポートされています。 会議のワークロードを展開して、[ダイヤルイン会議] オプションを選択すると、会議のお知らせアプリケーションが既定で自動的にインストールされ、有効になります。

  - **[ダイヤルイン会議の設定] ページ**   の [ダイヤルイン会議の設定] ページには、利用可能な言語が含まれている会議のダイヤルイン番号、割り当てられている会議情報 (スケジュールされていない会議)、会議中の DTMF コントロールが表示されます ダイヤルイン会議の設定ページは、Web サービスの一部として自動的にインストールされます。

  - **Lync server 2013、仲介サーバー、pstn ゲートウェイ**   のダイヤルイン会議には、lync server 2013 と pstn ゲートウェイの間でシグナリング (およびメディア) を変換するための仲介サーバーと、仲介サーバーと pstn ゲートウェイ間のシグナリングとメディアを変換する pstn ゲートウェイが必要です。 ダイヤルイン会議の場合、少なくとも1つの仲介サーバーと、少なくとも次のいずれかを展開する必要があります。
    
      - PSTN ゲートウェイ
    
      - IP-PBX
    
      - セッション ボーダー コントローラー (SBC) (SIP トランクを構成して接続するインターネット テレフォニー サービス プロバイダー (ITSP) のため)
    
    <div>
    

    > [!NOTE]  
    > エンタープライズ Voip も展開している場合、仲介サーバーと PSTN ゲートウェイはエンタープライズ Voip 展開の一部です。 エンタープライズ Voip を展開していない場合は、少なくとも1つの仲介サーバーと、少なくとも1つの PSTN ゲートウェイ、IP PBX、またはダイヤルイン会議用の SBC を展開する必要があります。

    
    </div>

  - **ファイルストア**   ファイルストアは、記録された名前のオーディオファイルに使用されます。 ファイルストアは、すべての Enterprise Edition または Standard Edition の展開における標準的なコンポーネントです。

  - **ユーザーストアの**   ユーザーストアは、Lync Server 2013 pin を保存するために使用されます。 ピンはハッシュされています。 ユーザーストアは、すべての Enterprise Edition または Standard Edition の展開における標準的なコンポーネントです。

  - **Lync server コントロールパネル**   lync server コントロールパネルを使用して、一部のダイヤルイン設定を構成できます。

  - **Lync server 管理シェル**   lync server 管理シェルコマンドレットを使用して、すべてのダイヤルイン設定を構成できます。 Lync Server 管理シェルコマンドレットを使用して、会議アテンダントアプリケーションと会議アナウンスメントアプリケーションの展開、構成、実行、監視、トラブルシューティングを行うことができます。 特定のコマンドレットの詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。

</div>

<div>

## <a name="supported-topologies"></a>サポートされるトポロジ

Lync Server 2013 では、会議サービスを実行しているサーバーは、常にフロントエンドサーバーまたは Standard Edition サーバーと併置されます。 最初の展開時に、トポロジビルダーにより、お客様のトポロジに会議を含めるオプションが提供されます。 また、トポロジ ビルダーを使用して、既存の展開に会議を追加することもできます。 詳細については、「 [Lync Server 2013 でトポロジを定義して構成する](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。

<div>

## <a name="dial-in-conferencing-toplogies"></a>会議 Toplogies でダイヤルする

ダイヤルイン会議は、次のトポロジと構成で展開できます。

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - エンタープライズ VoIP の有無は問いません

アプリケーションサービス、会議アテンダントアプリケーション、会議のお知らせアプリケーションはセントラルサイトに展開できますが、ブランチサイトでは展開できません。

<div>


> [!NOTE]  
> ダイヤルイン会議を展開する場合は、Lync Server 2013 会議を展開するすべてのプールに展開する必要があります。 プールごとにアクセス番号を割り当てる必要はありませんが、プールごとにダイヤルイン会議機能を展開する必要があります。 この要件では、ユーザーが1つのプールのアクセス番号を呼び出して Lync Server 2013 会議に別のプールで参加した場合に、記録された名前の機能がサポートされます。



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Lync Server 2013 および Office Web Apps でサポートされているトポロジ

Lync Server 2013 では、次の方法で Office Web Apps サーバーを構成できます。 必要に応じて次のことができます。

  - **Lync Server 2013 と Office Web Apps サーバーの両方をオンプレミスの組織のファイアウォールと同じネットワークゾーンにインストールします。** このトポロジでは、Office Web Apps サーバーへの外部アクセスがリバースプロキシサーバーによって提供されます。 Lync Server 2013 と Office Web Apps サーバー (または Office Web Apps サーバーファーム) の両方がオンプレミスと組織のファイアウォールの背後にインストールされている。 理想的には、Lync Server と同じネットワークゾーンに Office Web Apps サーバーをインストールすることをお勧めします。
    
    外部の Lync クライアントは、インターネットからの要求を受け取り、内部ネットワークに転送するサーバーであるリバースプロキシサーバーを使用して、Lync Server 2013 および Office Web Apps Server に接続できます。 (内部クライアントは、Office Web Apps サーバーに直接接続できるため、リバースプロキシサーバーを使用する必要はありません)。このトポロジは、Lync Server 2013 のみで使用される専用の Office Web Apps サーバーファームを使用する場合に最適です。

  - **外部で展開された Office Web Apps サーバーを使用する**
    
    このトポロジでは、Lync Server 2013 はオンプレミスで展開され、Lync Server ネットワークゾーンの外部に展開されている Office Web Apps サーバーを使用します。 この問題は、Office Web Apps サーバーが企業内の複数のアプリケーション間で共有されており、Lync Server が Office Web Apps サーバーの外部インターフェイスを使用する必要があるネットワークに展開されている場合に発生することがあります。
    
    リバースプロキシサーバーをインストールする必要はありません。代わりに、Office Web Apps サーバーから Lync Server 2013 へのすべての要求は、Edge サーバー経由でルーティングされます。 内部と外部の Lync クライアントの両方が、外部 URL を使用して Office Web Apps サーバーに接続されます。
    
    Office Web Apps サーバーが内部ファイアウォールの外側に展開されている場合は、[Office Web Apps Server] が [トポロジビルダー] の**外部ネットワーク ([境界/インターネット]) に展開**されていることを選択します。 詳細については[、「Office Web Apps Server および Lync server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

選択するトポロジにかかわらず、ファイアウォールの正しいポートを開くことは重要です。 DNS 名、IP アドレス、およびポートが、Office Web Apps サーバー、ロードバランサー、または Lync サーバー上のファイアウォールによってブロックされていないことを確認する必要があります。

<div>


> [!NOTE]  
> Office Web Apps サーバーへの外部アクセスを提供するもう1つの方法は、境界ネットワークにサーバーを展開することです。 Office Web Apps サーバーのセットアップでは、サーバーコンピューターが Active Directory ドメインのメンバーである必要があることに注意してください。 ネットワークポリシーで境界ネットワーク内のコンピューターが Active Directory ドメインメンバーになることを許可していない場合は、境界ネットワークに Office Web Apps サーバーをインストールしないことをお勧めします。 代わりに、内部ネットワークに Office Web Apps サーバーをインストールし、リバースプロキシサーバー経由で外部ユーザーのアクセスを提供する必要があります。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

