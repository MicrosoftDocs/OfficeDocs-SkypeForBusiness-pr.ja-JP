---
title: 各種ポリシーの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a105ea62b82d904007a2faa0493fd17092b84462
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a>各種ポリシーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-24_

<div>

## <a name="configuring-the-various-policies"></a>各種ポリシーの構成

Lync Server 2013 のストレスとパフォーマンスツールを実行する前に、Lync Server 2013 トポロジで構成できる各種のポリシーを次に示します。

<div>

## <a name="configuring-the-archiving-policy"></a>アーカイブポリシーを構成する

「スクリプト ArchivingPolicy の例を参照してください。 このスクリプトは、アーカイブサーバーがトポロジに展開されている場合にのみ使用する必要があります。 詳細については、「lync Server 2013 のドキュメントとコマンドレットのヘルプ」を参照してください。 [lync server 2013 のコマンドレットのアーカイブと監視](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\))を行います。

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>会議ポリシーを構成する

「スクリプト会議ポリシー ps1」の例を参照してください。 詳細については、「lync Server 2013 ドキュメント」および「 [Lync server 2013 の Web 会議コマンド](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\))レットのヘルプ」を参照してください。

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>連絡先ポリシーを構成する

例 ContactsPolicy を参照してください。 詳細については、「lync Server 2013 ドキュメント」および「 [Lync server 2013 の IM とプレゼンスのコマンド](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\))レットのヘルプ」を参照してください。

</div>

<div>

## <a name="configuring-the-federation-policy"></a>フェデレーションポリシーを構成する

例 FederationPolicy を参照してください。 詳細については、「lync server 2013 ドキュメント」および「lync server 2013 での microsoft Lync Server 2013 および[フェデレーションと外部アクセスコマンド](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\))レットの[Edge server コマンド](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\))レットのヘルプ」を参照してください。

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>通話受付制御ポリシーを構成する

例 BandwidthPolicy を参照してください。 詳細については、lync server 2013 の「[通話受付制御](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\))」と「lync server [2013 での通話受付制御コマンド](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\))レットのヘルプ」を参照し2013てください。

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>ボイスルーティングルールを構成する

例 RoutingRules を参照してください。 ボイスルーティングルールを構成するときは、電話のコンテキスト (¥ Location Profile または/simplename) と内部/外部の市外局番をメモして、ユーザーの作成時と LyncPerfTool の構成時に指定できるようにします (特にPSTN-UC および UC-PSTN)。 たとえば、RoutingRules の例の**CsDialPlan**コマンドレットの呼び出しの simplename パラメーターは、UserProfileGenerator の次の図の locationprofile 値に使用する必要があります。

![ボイスルーティングルールの例。](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "ボイスルーティングルールの例。")

詳細については、「lync Server 2013 ドキュメント」および「 [Lync server 2013 のエンタープライズボイスコマンド](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\))レットのヘルプ」を参照してください。

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>会議アテンダントアプリケーションの構成

例 ConferenceAutoAttendantConfiguration を参照してください。 ConferencingAutoAttendant 電話番号 (既定では 1121111111) をメモし、それを構成の生成用の LyncPerf ツール構成ツールに入力できるようにします。

![会議アテンダントアプリケーションの構成](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "会議アテンダントアプリケーションの構成")

詳細については、「lync server 2013 ドキュメント」および「lync server 2013 での[Web 会議コマンド](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\))レットのヘルプ (lync server 2013 および[ダイヤルイン会議コマンド](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\))レットのヘルプ)」を参照してください。

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>Lync Server コールパークサービスの構成

コールパークは既定では無効になっています。 「CallParkConfiguration」の例を参照してください。 詳細については、「lync Server 2013 ドキュメント」および「 [Lync server 2013 のコールパークアプリケーションコマンドレット](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\))のヘルプ」を参照してください。

</div>

<div>

## <a name="configuring-emergency-calls"></a>緊急通話の設定

緊急通話のストレスとパフォーマンスのテストを構成するには、次の手順を実行します。

1.  緊急通話のためのボイスルートを設定します。 このボイスルートを設定する例については、「コメント "E911 にルーティングする RoutingRules」の説明を参照してください。
    
    <div>
    

    > [!WARNING]  
    > RoutingRules の例のコマンドには、911ではなく数値119を含む数値パターンが含まれています。 ロードテスト中に、ローカルの緊急電話会社に誤って通話を発信しないようにするには、911 (または実際のローカル緊急電話番号) の使用を避ける必要があります。 この構成は、シミュレーション目的でのみ使用されます。

    
    </div>

2.  次の図に示すように、Userプロビジョニングツールの [ **LIS** ] タブの値を入力して、アドレスを構成します。
    
    ![位置情報サービスを構成します。](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "位置情報サービスを構成します。")  

3.  [ **LIS 構成ファイルの生成**] をクリックします。

4.  ポート、サブネット、スイッチ、ワイヤレスアクセスポイント (Wap) の CSV ファイル、および Lync Server 2013 ストレスおよびパフォーマンスツール用の XML ファイルが生成されます。 CSV ファイルは、LisConfiguration スクリプトを使用して位置情報サービス (LIS) を構成するときに、同じフォルダー内で入力として使用されます。 生成された Locations0 ファイルを、Lync Server 2013 のストレスとパフォーマンスツールの実行可能ファイル (LyncPerfTool) と同じフォルダーに移動します。これにより、位置情報プロファイル (ダイヤルプラン) のシナリオが実行されます。

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>ユーザーの作成、有効化、構成、無効化

次のスクリプトを実行する前に、すべてのユーザーを作成する必要があります。 「ユーザー[と連絡先を作成して](create-users-and-contacts.md)ユーザーを作成する」の手順に従います。 詳細については、「[ユーザー](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))用の Lync Server 2013 コマンドレット」を参照してください。また[](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) 、「ユーザーの[設定](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\))」を参照してください。

</div>

<div>

## <a name="configuring-response-group-application"></a>応答グループアプリケーションを構成する

ResponseGroupConfiguration ps1 の例を参照してください。 詳細については、「Lync Server 2013 ドキュメント」および「 [lync server 2013 のグループアプリケーションコマンドレットに応答](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\))するためのコマンドレットのヘルプ」を参照してください。応答グループのアプリケーション構成を確認するに`https://<poolfqdn>/RgsConfig/`は、次の図のように「」を参照してください。

![応答グループ構成ツール。](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "応答グループ構成ツール。")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

