---
title: 'Lync Server 2013: モビリティの要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0eeb3feda41a62472c79214681bc4b9ce0a22ee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Lync Server 2013 のモビリティ要件の定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync 2010 Mobile および Lync 2013 Mobile クライアントを使用している場合は、Lync Server 2013 モビリティ機能の計画フェーズで、展開の手順を決定する決定を行います。

考慮する必要がある決定事項は次のとおりです。

  - **Lync モバイル クライアントで、自動検出を使用しますか。**
    
    自動検出をサポートする必要がある場合は、新しい内部および外部のドメインネームシステム (DNS) レコードを作成し、フロントエンドサーバー、ディレクター、リバースプロキシの証明書にサブジェクトの別名を追加して、既存の公開ルールを変更する必要があります。リバースプロキシで。 詳細については、「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。 自動検出を使用すると、ユーザーは、モバイルデバイスの設定に Url を入力することなく、企業ネットワークの内外にある任意の場所から Lync Server 2013 Web サービスを自動的に検索できます。
    
    自動検出の代わりに手動設定を使用する場合、モバイルユーザーはモバイルデバイスに以下の Url を手動で入力する必要があります。
    
      - 外部\<アクセス用の\>Https://extpoolfqdn/autodiscover/autodiscoverservice.svc/root (
    
      - https://\<intpoolfqdn\>/AutoDiscover/autodiscoverservice 内部アクセス用のルート
    
    自動検出を使用することを強くお勧めします。手動設定を使用するのは、主にトラブルシューティングを行う場合です。

  - **自動検出のサポートを決めた場合は、SIP ドメインごとにサブジェクトの別名でリバース プロキシ上の証明書を更新しますか。**
    
    SIP ドメインが多い場合、リバース プロキシ上のパブリック証明書の更新は非常に高コストになる可能性があります。 その場合は、ポート443で HTTPS を使用するのではなく、最初の自動検出サービス要求がポート80で HTTP を使用するように自動検出を実装することを選択できます。 ただし、これは推奨されている方法ではありません。 この代替方法を選択する場合は、リバースプロキシの証明書を更新する必要はありませんが、ポート80で HTTP 用の web 公開ルールを作成する必要があります。 詳細については、「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。

  - **企業ネットワークの内外で Lync モバイル クライアントをサポートしますか。または企業ネットワークの内部のみでクライアントをサポートしますか。**
    
    企業ネットワークの内外でモバイル クライアントをサポートする場合は、モバイル デバイスはどの場所からでもモビリティ機能にアクセスできます。既定の構成は、企業ネットワークの内外でクライアントをサポートするようになっています
    
    既定の構成では、モバイル クライアントのトラフィックが外部サイトを経由することを許可していますが、モバイル クライアントのトラフィックを内部企業ネットワークに制限することができます。 トラフィックを内部ネットワークに制限すると、モバイル デバイスが企業ネットワーク内に存在する場合に限り、ユーザーはそのモバイル デバイス上で Lync モバイル アプリケーションを使用できます。
    
    Mcx mobility service と Lync 2010 Mobile を使用したモビリティをサポートする展開では、 **Set-CsMcxConfiguration**コマンドレットを実行します。 内部使用のみのモビリティを設定するには、次のようなコマンドを使用します。
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > UCWA には、追加の構成は必要ありません。 UCWA には、それに相当する内部のみの構成がありません。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Lync server 2013&nbsp;フロントエンドサーバーまたはフロントエンドプールを使用していて、lync server&nbsp;2010 フロントエンドサーバーまたはフロントエンドプールを使用して<STRONG>いない</STRONG>場合は、 <STRONG>cookie ベースの永続化の要件はありません</STRONG>。 Lync Server 2010&nbsp;のフロントエンドサーバーまたはフロントエンドプールを保持する必要がある場合は、引き続き、cookie ベースの永続化のために lync server 2010 の場合と同じルールが適用されます。

    
    </div>

  - **Apple iOS デバイスと Windows Phone でプッシュ通知をサポートしますか。**
    
    プッシュ通知をサポートすると、サポートされている Apple iOS デバイスと Windows Phone は、モバイル アプリケーションが非アクティブな場合に発生するイベントの通知を受け取ります。 Lync Online データセンターにあるクラウドベースの Lync Server プッシュ通知サービスとのフェデレーション関係を持つようにエッジサーバーを構成し、コマンドレットを実行してプッシュ通知を有効にする必要があります。
    
    Wi-fi ネットワーク経由のプッシュ通知をサポートする必要がある場合は、モバイルデバイスプロバイダーの3G またはデータネットワークでプッシュ通知をサポートすることに加えて、エンタープライズ Wi-fi ネットワーク上でポート5223アウトを開く必要があります。 Wi-Fi ネットワークでプッシュ通知をサポートすると、Wi-Fi のみを使用するモバイル デバイスと室内での受信が弱いモバイル デバイスがサポートされます。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2010 モバイルクライアントを実行している Apple デバイスをサポートする場合にのみ、ポート TCP 5223 を開く必要があります。

    
    </div>
    
    プッシュ通知をサポートしていない場合、Apple モバイルデバイスおよび Windows Phone のユーザーは、モバイルアプリケーションが非アクティブな場合に発生するインスタントメッセージの招待や不在着信メッセージなどのイベントについては確認できません。
    
    <div>
    

    > [!NOTE]  
    > Apple デバイス上の Lync 2013 モバイルクライアントは、プッシュ通知を必要としません。 Windows Phone 上の Lync 2013 モバイルクライアントは、プッシュ通知を使用します。 プッシュ通知およびプッシュ通知クリアリングハウスの計画は、lync 2013 Mobile クライアントを実行できない Windows Phone および Apple のデバイス上の Lync Mobile に対して同じままです。

    
    </div>

  - **すべてのユーザーがモビリティ機能にアクセスできるようにするか、またはこれらの機能にアクセスできるユーザーを指定できるようにしますか。**
    
    Lync Server 2013 でユーザーが使用できる機能について説明します。 既定では、勤務先から通話、ボイスオーバー IP (VoIP) を許可、モビリティを有効にできます。 利用可能なオプションの全セットを次に示します。
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Feature/Parameter Name/Scope (ポリシーパラメーター名が同じではない可能性があります)</th>
    <th>説明</th>
    <th>導入</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>モビリティを有効にする</p>
    <p>パラメーター名:<code>EnableMobility</code></p>
    <p>範囲: グローバル/サイト/ユーザー</p></td>
    <td><p>管理者設定 Lync Mobile がインストールされている特定のスコープ内のユーザーを制御するには、ポリシーが False に設定されている場合、ユーザーはクライアントにサインインできません。</p>
    <p>既定値は True です。</p></td>
    <td><p>Lync Server 2010 の累積的な更新プログラム:11 月2011</p></td>
    </tr>
    <tr class="even">
    <td><p>外部音声を有効にする</p>
    <p>パラメーター名:<code>EnableOutsideVoice</code></p>
    <p>範囲: グローバル/サイト/ユーザー</p></td>
    <td><p>ユーザーが携帯電話番号ではなく勤務先番号を使用して通話を発信または受信できるようにする機能を、勤務先から通話を使用できるように制御します。 False に設定されている場合、ユーザーはモバイルデバイスから自分の勤務先番号を使用して通話を発信または受信できません。</p>
    <p>既定値は True です。</p></td>
    <td><p>Lync Server 2010 の累積的な更新プログラム:11 月2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP オーディオおよびビデオを有効にする</p>
    <p>パラメーター名:<code>EnableIPAudioVideo</code></p>
    <p>範囲: グローバル/サイト/ユーザー</p></td>
    <td><p>ユーザーが VoIP を使用して、モバイルデバイスで音声またはビデオ通話を発信または受信できるようにするかどうかを制御します。 False に設定されている場合、ユーザーはデバイス上で VoIP またはビデオ通話を発信または受信できません。</p>
    <p>既定値は True です。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>IP オーディオに WiFi が必要</p>
    <p>パラメーター名:<code>RequireWiFiForIPAudio</code></p>
    <p>範囲: グローバル/サイト/ユーザー</p></td>
    <td><p>この設定では、携帯データネットワークではなく、Wi-fi で VoIP 経由の通話を発信および受信するためにクライアントが必要かどうかを定義します。 True に設定すると、ユーザーは WiFi ネットワークに接続されている場合にのみ VoIP 通話を発信および受信できるようになります。</p>
    <p>既定値は False です。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP ビデオに WiFi が必要</p>
    <p>パラメーター名:<code>RequireWiFiForIPVideo</code></p>
    <p>範囲: グローバル/サイト/ユーザー</p></td>
    <td><p>この設定では、携帯データネットワークではなく、Wi-fi でビデオ通話を発信および受信するためにクライアントが必要かどうかを定義します。 True に設定すると、ユーザーは Wi-fi ネットワークに接続されている場合にのみ、ビデオ通話を発信および受信できます。</p>
    <p>既定値は False です。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    構成できるポリシー設定、およびポリシーを管理する方法については、「 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)」、「 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)」、「 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)」、「 [Get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) 」、および「 [Remove-get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)」を参照してください。

  - **エンタープライズ VoIP が有効になっていないユーザーが、クリックして参加を使用して会議に参加できるようにしますか。**
    
    モビリティ機能や勤務先電話からの通話機能にアクセスできるユーザーは、エンタープライズ VoIP が有効になっている必要があります。 ただし、エンタープライズ Voip が有効になっていないユーザーは、適切な音声ポリシーが割り当てられている場合は、モバイルデバイスでリンクをクリックすることで会議に参加できます。 特定の音声ポリシーをこれらのユーザーに割り当てるか、グローバルポリシーまたはサイトレベルのポリシーが適用されるようにすることができます。 割り当てる音声ポリシーには、公衆交換電話網 (PSTN) 使用法レコードと、ユーザーが会議に参加するためにダイヤルアウトできる領域を定義するルートがある必要があります。 音声ポリシー、PSTN 使用法レコード、およびルートの設定の詳細については、「 [Lync Server 2013 での音声ポリシー、pstn 使用法レコード、およびボイスルートの構成](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > モバイルデバイス上のリンクをクリックすると Lync Server 2013 からの発信通話が発生するため、クリックして参加するモバイルユーザーには音声ポリシーと関連する PSTN 使用法レコードおよび音声ルートが必要です。

    
    </div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)  


[Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイスルートの構成](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

