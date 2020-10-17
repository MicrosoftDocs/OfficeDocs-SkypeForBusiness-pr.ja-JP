---
title: さまざまなポリシーの構成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0abb428dab96c09c7cd8b82d99de12ba76068eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505244"
---
# <a name="configuring-the-various-policies"></a>さまざまなポリシーの構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-24_

<div>

ここでは、lync Server 2013 ストレスおよびパフォーマンスツールを実行する前に、Lync Server 2013 トポロジで構成できるさまざまなポリシーについて説明します。

<div>

## <a name="configuring-the-archiving-policy"></a>アーカイブポリシーの構成

スクリプト ArchivingPolicy.ps1 の例を参照してください。 このスクリプトは、アーカイブサーバーがトポロジに展開されている場合にのみ使用する必要があります。 詳細については、「lync server 2013 のドキュメントとコマンドレットのヘルプ」を参照してください。 [Lync server 2013 でのコマンドレットのアーカイブおよび監視](https://technet.microsoft.com/library/gg415629\(v=ocs.15\))について説明します。

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>会議ポリシーの構成

スクリプト MeetingPolicy.ps1 の例を参照してください。 詳細については、「lync server 2013 のドキュメント」および「 [Lync server 2013 での Web 会議のコマンド](https://technet.microsoft.com/library/gg415675\(v=ocs.15\))レットに関するヘルプ」を参照してください。

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>連絡先ポリシーを構成する

ContactsPolicy.ps1 の例を参照してください。 詳細については、「lync server 2013 のドキュメントと、 [Lync server 2013 の IM およびプレゼンスのコマンド](https://technet.microsoft.com/library/gg398611\(v=ocs.15\))レットのヘルプ」を参照してください。

</div>

<div>

## <a name="configuring-the-federation-policy"></a>フェデレーションポリシーを構成する

FederationPolicy.ps1 の例を参照してください。 詳細については、「lync server 2013 での [エッジサーバーのコマンドレット](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) 」および「lync server [2013 でのフェデレーションと外部アクセスのコマンド](https://technet.microsoft.com/library/gg415651\(v=ocs.15\))レットのための lync server 2013 ドキュメントとコマンドレットのヘルプ」を参照してください。

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>通話受付管理ポリシーの構成

BandwidthPolicy.ps1 の例を参照してください。 詳細については、lync server [2013 の通話受付管理の](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) lync server 2013 ドキュメントの概要と、 [lync server 2013 での通話受付管理のコマンド](https://technet.microsoft.com/library/gg415676\(v=ocs.15\))レットのヘルプを参照してください。

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>音声ルーティングルールの構成

RoutingRules.ps1 の例を参照してください。 音声ルーティングルールを構成するときは、電話のコンテキスト (つまり、[場所のプロファイル] または [simplename]) と [内部/外部] エリアコードをメモしてください。これにより、ユーザーの作成時および LyncPerfTool の構成 (特に PSTN と UC) の間にそれらを指定できるようになります。 たとえば、RoutingRules.ps1 の例の **get-csdialplan** コマンドレットの simplename パラメーターは、UserProfileGenerator.exe の次の図の locationprofile 値に使用する必要があります。

![音声ルーティングルールの例。](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "音声ルーティングルールの例。")

詳細については、「lync server 2013 のドキュメント」および「 [Lync server 2013 でのエンタープライズ voip のコマンド](https://technet.microsoft.com/library/gg415658\(v=ocs.15\))レットのヘルプ」を参照してください。

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>会議アテンダントアプリケーションを構成する

ConferenceAutoAttendantConfiguration.ps1 の例を参照してください。 ConferencingAutoAttendant 電話番号 (既定では 1121111111) をメモして、構成を生成するために LyncPerf ツール構成ツールに入力できるようにします。

![会議アテンダントアプリケーションを構成する](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "会議アテンダントアプリケーションを構成する")

詳細については、lync server [2013 の Web 会議](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) のコマンドレットおよび lync [Server 2013 のダイヤルイン会議](https://technet.microsoft.com/library/gg415630\(v=ocs.15\))のコマンドレットについて、lync server 2013 のドキュメントとコマンドレットのヘルプを参照してください。

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>Lync Server コールパークサービスの構成

コールパークは既定で無効になっています。 CallParkConfiguration.ps1 の例を参照してください。 詳細については、「lync server 2013 のドキュメント」および「 [Lync server 2013 のコールパークアプリケーションのコマンド](https://technet.microsoft.com/library/gg415639\(v=ocs.15\))レットに関するヘルプ」を参照してください。

</div>

<div>

## <a name="configuring-emergency-calls"></a>緊急電話の構成

次の手順を実行して、緊急電話のストレスとパフォーマンスのテストを構成します。

1.  緊急電話の音声ルートを設定します。 この音声ルートを設定する例については、「E911 から PSTN へのルーティング」のコメントの下にある RoutingRules.ps1 スクリプトを参照してください。
    
    <div>
    

    > [!WARNING]  
    > RoutingRules.ps1 のコマンドの例では、911ではなく、119の数値パターンが指定されています。 ロードテスト時にローカルの緊急対応オペレーターを誤って呼び出すことを防ぐには、911 (または実際のローカル緊急電話番号) を使用しないようにする必要があります。 この構成はシミュレーションのみを目的としています。

    
    </div>

2.  次の図に示すように、Userプロビジョニングツールの [ **LIS** ] タブで値を入力して、アドレスを構成します。
    
    ![場所情報サービスを構成します。](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "場所情報サービスを構成します。")  

3.  [ **LIS Config ファイルの生成**] をクリックします。

4.  ポート、サブネット、スイッチ、ワイヤレスアクセスポイント (Wap) の CSV ファイル、および Lync Server 2013 ストレスおよびパフォーマンスツール用の XML ファイルが生成されます。 CSV ファイルは、LisConfiguration.ps1 スクリプトを使用して場所情報サービス (LIS) を構成するときに、同じフォルダー内の入力として使用されます。 生成された Locations0.xml ファイルを、Lync Server 2013 ストレスおよびパフォーマンスツールの実行可能ファイル (LyncPerfTool.exe) と同じフォルダーに移動します。これにより、場所プロファイル (ダイヤルプラン) のシナリオが実行されます。

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>ユーザーの作成、有効化、構成、無効化

次のスクリプトを実行する前に、すべてのユーザーを作成する必要があります。 [ [ユーザーと連絡先を作成](create-users-and-contacts.md) する] の指示に従って、ユーザーを作成します。 詳細については、「 [get-help](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))user」、「 [Set-csuser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))」、および「 [Disable-Csuser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) コマンドレット」の Lync Server 2013 コマンドレットのドキュメントを参照してください。

</div>

<div>

## <a name="configuring-response-group-application"></a>応答グループアプリケーションの構成

ResponseGroupConfiguration.ps1 の例を参照してください。 詳細については、lync server 2013 のドキュメントとコマンドレットのヘルプを参照してください。 [Lync server 2013 の応答グループアプリケーションのコマンドレット](https://technet.microsoft.com/library/gg415654\(v=ocs.15\))を参照してください。応答グループアプリケーションの構成を確認するには、 `https://<poolfqdn>/RgsConfig/` 次の図に示すように「」を参照してください。

![応答グループ構成ツール。](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "応答グループ構成ツール。")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

