---
title: 'Lync Server 2013: モビリティの要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 604812d96f58a53ee008bfe42603243571138d1e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Lync Server 2013 でのモビリティの要件の定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync 2010 Mobile および Lync 2013 モバイルクライアントを使用している場合、Lync Server 2013 のモバイル機能の計画フェーズでは、展開の手順を決定する意思決定を行います。

考慮する必要がある決定事項は次のとおりです。

  - **Lync モバイルクライアントの自動検出を使用しますか?**
    
    自動検出をサポートする必要がある場合は、新しい内部および外部ドメインネームシステム (DNS) レコードを作成し、フロントエンドサーバー、ディレクター、リバースプロキシ上の証明書にサブジェクトの代替名を追加して、既存の公開ルールを変更する必要があります。リバースプロキシ。 詳細については、「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。 自動検出を使用すると、ユーザーは、モバイルデバイスの設定で Url を入力しなくても、企業ネットワークの内外の任意の場所から Lync Server 2013 Web サービスを自動的に見つけることができます。
    
    自動検出の代わりに手動の設定を使用する場合、モバイルユーザーは、モバイルデバイスに次の Url を手動で入力する必要があります。
    
      - 外部\<アクセス用の\>Https://extpoolfqdn/Autodiscover/autodiscoverservice.svc/Root
    
      - https://\<intpoolfqdn\>/AutoDiscover/autodiscoverservice、内部アクセス用のルート
    
    自動検出を使用することを強くお勧めします。 手動設定の主な用途は、トラブルシューティングです。

  - **自動検出をサポートすることにした場合、リバースプロキシの証明書を各 SIP ドメインのサブジェクト別の名前を使用して更新する必要がありますか?**
    
    SIP ドメインが多い場合は、リバースプロキシのパブリック証明書を更新すると非常にコストがかかることがあります。 この場合は、自動検出を実装して、HTTPS をポート443で使う代わりに、最初の自動検出サービス要求でポート80に対して HTTP を使うようにすることができます。 ただし、この方法はお勧めできません。 この代替を選択する場合は、リバースプロキシで証明書を更新する必要はありませんが、HTTP 用の web 公開ルールは、ポート80で作成する必要があります。 詳細については、「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。

  - **企業ネットワークの内部と外部の両方の Lync モバイルクライアントをサポートしますか。または企業ネットワーク内でのみサポートされているクライアントをサポートしますか?**
    
    ネットワークの内部と外部のモバイルクライアントをサポートしたい場合、モバイルデバイスはどこからでもモビリティ機能にアクセスできます。 既定の構成では、社内ネットワークと社外のクライアントの両方をサポートします。
    
    既定の構成では、モバイルクライアントトラフィックが外部サイトを通過できるようになりますが、モバイルクライアントトラフィックを内部の企業ネットワークに制限することができます。 内部ネットワークへのトラフィックを制限すると、ユーザーは、ネットワーク内にいるときにのみ、モバイルデバイスで Lync モバイルアプリケーションを使用できます。
    
    Mcx mobility service と Lync 2010 Mobile を使ったモビリティをサポートする展開の場合は、 **Set-CsMcxConfiguration**コマンドレットを実行します。 内部使用のためだけにモバイル機能を設定するには、次のようなコマンドを使用します。
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > UCWA には、その他の構成は必要ありません。 UCWA には、相当する内部専用構成がありません。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server&nbsp;2013 フロントエンドサーバーまたはフロントエンドプールを使用してい<STRONG></STRONG>て、Lync Server 2010&nbsp;フロントエンドサーバーまたはフロントエンドプールを使っていない場合は、 <STRONG>cookie ベースの常設は必要ありませ</STRONG>ん。 Lync Server 2010&nbsp;フロントエンドサーバーまたはフロントエンドプールを保持する必要がある場合は、依然として、cookie ベースの常設用に lync server 2010 の場合と同じ規則が適用されます。

    
    </div>

  - **Apple iOS デバイスと Windows Phone のプッシュ通知をサポートしますか?**
    
    プッシュ通知をサポートしている場合、サポートされている Apple iOS デバイスと Windows Phone は、モバイルアプリケーションが非アクティブなときに発生するイベントの通知を受け取ります。 エッジサーバーは、Lync Online データセンターにあるクラウドベースの Lync Server プッシュ通知サービスとのフェデレーション関係を持ち、プッシュ通知を有効にするコマンドレットを実行するように構成する必要があります。
    
    Wi-fi ネットワーク経由でのプッシュ通知をサポートする場合は、モバイルデバイスプロバイダーの3G またはデータネットワーク経由でのプッシュ通知のサポートに加えて、エンタープライズ Wi-fi ネットワークでポート5223を開く必要があります。 Wi-fi ネットワーク経由でのプッシュ通知のサポートには、不適切な室内受信の Wi-fi とモバイルデバイスのみを使用するモバイルデバイスがサポートされています。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2010 モバイルクライアントを実行している Apple デバイスをサポートしている場合にのみ、ポート TCP 5223 を開く必要があります。

    
    </div>
    
    プッシュ通知がサポートされていない場合は、Apple モバイルデバイスおよび Windows Phone のユーザーは、モバイルアプリケーションが非アクティブなときに発生する、インスタントメッセージの招待状や不在着信メッセージなどのイベントについては検出されません。
    
    <div>
    

    > [!NOTE]  
    > Apple デバイス上の Lync 2013 モバイルクライアントでは、プッシュ通知は必要ありません。 Windows Phone の Lync 2013 モバイルクライアントでは、プッシュ通知が使われます。 プッシュ通知の計画とプッシュ通知のクリアリングハウスは、Lync 2013 モバイルクライアントを実行できない Windows Phone および Apple デバイス上の Lync Mobile でも同じです。

    
    </div>

  - **すべてのユーザーがモビリティ機能にアクセスできるようにするか、これらの機能にアクセスできるユーザーを指定できるようにする必要がありますか。**
    
    この表では、Lync Server 2013 でユーザーが使用できる機能について説明します。 既定では、勤務先での通話が許可され、ボイスオーバー IP (VoIP) が許可され、モビリティが有効になります。 使用可能なオプションの全セットを次に示します。
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Feature/Parameter Name/Scope (ポリシーパラメーター名は同じではない可能性があります)</th>
    <th>説明</th>
    <th>導か</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>モビリティを有効にする</p>
    <p>パラメーター名:<code>EnableMobility</code></p>
    <p>スコープ: グローバル/サイト/ユーザー</p></td>
    <td><p>管理者設定 Lync Mobile がインストールされている特定のスコープでユーザーを制御するには、ポリシーを False に設定すると、ユーザーはクライアントにサインインできなくなります。</p>
    <p>既定の設定は True です。</p></td>
    <td><p>Lync Server 2010 の累積更新プログラム: 2011 年11月</p></td>
    </tr>
    <tr class="even">
    <td><p>外部音声を有効にする</p>
    <p>パラメーター名:<code>EnableOutsideVoice</code></p>
    <p>スコープ: グローバル/サイト/ユーザー</p></td>
    <td><p>勤務先のユーザーが通話を使用する機能を制御します。この機能は、ユーザーが携帯電話番号の代わりに勤務先の電話番号を使って通話を発信および受信できるようにします。 False に設定した場合、ユーザーはモバイルデバイスから勤務先の電話番号を使用して通話を発信または受信することができなくなります。</p>
    <p>既定の設定は True です。</p></td>
    <td><p>Lync Server 2010 の累積更新プログラム: 2011 年11月</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP オーディオと IP ビデオを有効にする</p>
    <p>パラメーター名:<code>EnableIPAudioVideo</code></p>
    <p>スコープ: グローバル/サイト/ユーザー</p></td>
    <td><p>ユーザーがモバイルデバイスで VoIP を使用して音声通話またはビデオ通話を受信できるようにするかどうかを制御します。 False に設定すると、ユーザーはデバイスで VoIP またはビデオ通話を発信または受信できなくなります。</p>
    <p>既定の設定は True です。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>IP オーディオ用の WiFi が必要</p>
    <p>パラメーター名:<code>RequireWiFiForIPAudio</code></p>
    <p>スコープ: グローバル/サイト/ユーザー</p></td>
    <td><p>この設定は、携帯電話のデータネットワークではなく、WiFi 上の VoIP 経由での通話の発信と受信をクライアントが必要とするかどうかを定義します。 True に設定すると、ユーザーは WiFi ネットワークに接続している場合にのみ VoIP 通話を発信および受信できます。</p>
    <p>既定の設定は False です。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP ビデオ用の WiFi が必要</p>
    <p>パラメーター名:<code>RequireWiFiForIPVideo</code></p>
    <p>スコープ: グローバル/サイト/ユーザー</p></td>
    <td><p>この設定は、携帯電話のデータネットワークではなく、wi-fi でのビデオ通話の発信と受信をクライアントが要求するかどうかを定義します。 True に設定した場合、ユーザーは、Wi-fi ネットワークに接続されているときにのみビデオ通話を発信および受信できます。</p>
    <p>既定の設定は False です。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    構成可能なポリシー設定の説明とポリシーの管理方法については、「[新しい-set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)、 [Set-set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)、 [Get-set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)、 [Grant-set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [」を参照してください。Set-csmobilitypolicy を削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)します。

  - **エンタープライズ Voip が有効になっていないユーザーが、クリックして会議に参加できるようにしますか?**
    
    ユーザーがモバイル機能にアクセスし、勤務先から通話を発信できるようにするには、エンタープライズ Voip を有効にする必要があります。 ただし、エンタープライズ Voip を有効にしていないユーザーは、モバイルデバイス上のリンクをクリックすると、適切な音声ポリシーが割り当てられている場合に、会議に参加できます。 特定のボイスポリシーをこれらのユーザーに割り当てるか、グローバルポリシーまたはサイトレベルのポリシーが存在していることを確認することができます。 割り当てるボイスポリシーには、公衆交換電話網 (PSTN) 利用状況レコードと、ユーザーが電話会議にダイヤルアウトできる領域を定義するルートが含まれている必要があります。 ボイスポリシー、PSTN 使用状況レコード、およびルートの設定の詳細については、「 [Lync Server 2013 で音声ポリシー、pstn 使用状況レコード、および音声ルートを構成する](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > クリックして参加したいモバイルユーザーは、モバイルデバイスでリンクをクリックすると、Lync Server 2013 からの発信通話が発生するため、音声ポリシーと関連する PSTN 使用状況レコードと音声ルートが必要になります。

    
    </div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)  


[Lync Server 2013 での音声ポリシー、PSTN 使用状況レコード、および音声ルートの構成](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

