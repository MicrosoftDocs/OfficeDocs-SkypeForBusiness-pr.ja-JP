---
title: 'Lync Server 2013: モビリティの要件の定義'
TOCTitle: モビリティの要件の定義
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48273369
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのモビリティの要件の定義

 

_**トピックの最終更新日:** 2015-03-09_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 モビリティ機能の計画フェーズでは、 Lync 2010 Mobile および Lync 2013 のモバイル クライアントを使用している場合は、展開手順を決めるためにいくつかの決定を行う必要があります。

ここでは、検討する必要がある決定事項について説明します。

  - **Lync モバイル クライアントで、自動検出を使用しますか。**
    
    自動検出をサポートする場合は、内部および外部ドメイン ネーム システム (DNS) レコードを新しく作成し、サブジェクトの別名を、 フロント エンド サーバー、 ディレクター、およびリバース プロキシの証明書に追加し、さらにリバース プロキシで既存の公開ルールを変更する必要があります。詳細については、「[Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。自動検出を使用すると、ユーザーは、モバイル デバイス設定に URL を入力しなくても、企業ネットワーク内外のどこからでも自動的に Lync Server 2013 Web サービスを見つけることができます。
    
    自動検出の代わりに手動設定を使用する場合、モバイル ユーザーはモバイル デバイスに以下の URL を手動で入力する必要があります。
    
      - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access
    
      - https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root for internal access
    
    自動検出を使用することを強くお勧めします。手動設定を使用するのは、主にトラブルシューティングを行う場合です。

  - **自動検出のサポートを決めた場合は、SIP ドメインごとにサブジェクトの別名でリバース プロキシ上の証明書を更新しますか。**
    
    SIP ドメインが多い場合、リバース プロキシ上のパブリック証明書の更新は非常に高コストになる可能性があります。この場合には、最初の自動検出サービス要求がポート 443 で HTTPS を使用する代わりにポート 80 で HTTP を使用するような自動検出の実装を選択できます。ただし、この方法は推奨の方法ではありません。この方法を選択した場合は、リバース プロキシ上の証明書を更新する必要はありませんが、ポート 80 の HTTP に対応する Web 公開ルールを作成する必要があります。詳細については、「[Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。

  - **企業ネットワークの内外で Lync モバイル クライアントをサポートしますか。または企業ネットワークの内部のみでクライアントをサポートしますか。**
    
    企業ネットワークの内外でモバイル クライアントをサポートする場合は、モバイル デバイスはどの場所からでもモビリティ機能にアクセスできます。既定の構成は、企業ネットワークの内外でクライアントをサポートするようになっています
    
    既定の構成では、モバイル クライアントのトラフィックが外部サイトを経由することを許可していますが、モバイル クライアントのトラフィックを内部企業ネットワークに制限することができます。トラフィックを内部ネットワークに制限すると、モバイル デバイスが企業ネットワーク内に存在する場合に限り、ユーザーはそのモバイル デバイス上で Lync モバイル アプリケーションを使用できます。
    
    Mcx モビリティ サービスと Lync 2010 Mobile を使用してモビリティをサポートする展開の場合は、 **Set-CsMcxConfiguration** コマンドレットを実行します。内部使用専用のモビリティを設定するには、次のようなコマンドを使用します。
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    > [!NOTE]
    > UCWA には追加の設定は必要ありません。UCWA には、同等の内部使用専用の構成はありません。
    

    > [!IMPORTANT]
    > Lync Server 2013 のフロント エンド サーバーまたはフロント エンド プールを使用していて、Lync Server 2010 のフロント エンド サーバーまたはフロント エンド プールがない場合、<STRONG>Cookie ベースの永続性に関する要件はありません</STRONG>。Lync Server 2010 のフロント エンド サーバーまたはフロント エンド プールを保持する必要がある場合は、Cookie ベースの永続性に関して Lync Server 2010 と同じルールが適用されます。



  - **Apple iOS デバイスと Windows Phone でプッシュ通知をサポートしますか。**
    
    プッシュ通知をサポートすると、サポートされている Apple iOS デバイスと Windows Phone は、モバイル アプリケーションが非アクティブな場合に発生するイベントの通知を受け取ります。Lync Online データセンターにあるクラウドベースの Lync Server プッシュ通知サービスとのフェデレーション関係を維持するように エッジ サーバーを構成し、さらにプッシュ通知を有効にするコマンドレットを実行する必要があります。
    
    モバイル デバイス プロバイダーの 3G またはデータ ネットワークでプッシュ通知をサポートするだけでなく、Wi-Fi ネットワークでもプッシュ通知をサポートする場合は、エンタープライズ Wi-Fi ネットワークでポート 5223 を発信用としてオープンする必要があります。Wi-Fi ネットワークでプッシュ通知をサポートすると、Wi-Fi のみを使用するモバイル デバイスと室内での受信が弱いモバイル デバイスがサポートされます。
    

    > [!IMPORTANT]
    > ポート TCP 5223は、 Lync 2010 Mobile クライアントを実行する Apple デバイスをサポートする場合に限りオープンする必要です。

    
    プッシュ通知をサポートしない場合は、Apple モバイル デバイスおよび Windows Phone のユーザーは、モバイル アプリケーションが非アクティブな場合に発生するインスタント メッセージの招待状、不在着信のメッセージなどのイベントに気付かなくなります。
    
    > [!NOTE]
    > Apple デバイス上の Lync 2013 モバイル クライアントは、プッシュ通知を使用しません。 Windows Phone 上の Lync 2013 モバイル クライアントはプッシュ通知を使用します。プッシュ通知および Push Notification Clearing House の計画は、 Lync 2013 モバイル クライアントを実行できない Windows Phone および Apple デバイス上の Lync Mobile と同じです。


  - **すべてのユーザーがモビリティ機能にアクセスできるようにしますか。またはモビリティ機能にアクセスできるユーザーを指定できるようにしますか。**
    
    以下の表では、 Lync Server 2013 でユーザーが使用できる機能について説明します。既定では、勤務先から通話機能、ボイス オーバー IP (VoIP) 機能を利用でき、モビリティが有効になっています。ここでは、利用できるオプション一式を示します。
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>機能/パラメーター名/スコープ (ポリシーのパラメーター名は異なる場合があります)</th>
    <th>説明</th>
    <th>導入</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>モビリティを有効にする</p>
    <p>パラメーター名: <code>EnableMobility</code></p>
    <p>スコープ: グローバル/サイト/ユーザー</p></td>
    <td><p>Lync Mobile がインストールされている所定のスコープ内で、ユーザーを管理する管理設定。ポリシーが False に設定されている場合、ユーザーはクライアントにサインインできません。</p>
    <p>既定設定は True です。</p></td>
    <td><p>Lync Server 2010 の累積的な更新プログラム: 2011 年 11 月</p></td>
    </tr>
    <tr class="even">
    <td><p>外部音声を有効にする</p>
    <p>パラメーター名: <code>EnableOutsideVoice</code></p>
    <p>スコープ: グローバル/サイト/ユーザー</p></td>
    <td><p>ユーザーが [勤務先から通話] を使用できるかどうかを管理します。これは、ユーザーが、携帯電話番号ではなく勤務先の電話番号を使用して、電話をかけたり受けたりできるようにする機能です。False に設定されている場合は、勤務先の電話番号を使用して、自分の携帯電話で電話をかけたり受けたりすることはできません。</p>
    <p>既定設定は True です。</p></td>
    <td><p>Lync Server 2010 の累積的な更新プログラム: 2011 年 11 月</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP オーディオと IP ビデオを有効にする</p>
    <p>パラメーター名: <code>EnableIPAudioVideo</code></p>
    <p>スコープ: グローバル/サイト/ユーザー</p></td>
    <td><p>ユーザーが VoIP を使用して、自分の携帯電話で電話をかけたり受けたりすることができるかどうかを管理します。False に設定されている場合は、ユーザーは自分の携帯電話で VoIP またはビデオ通話を行うことができません。</p>
    <p>既定設定は True です。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>IP オーディオ用の WiFi が必要</p>
    <p>パラメーター名: <code>RequireWiFiForIPAudio</code></p>
    <p>スコープ: グローバル/サイト/ユーザー</p></td>
    <td><p>この設定では、クライアントが、携帯電話会社の回線ではなく WiFi の VoIP を使用して電話をかけたり受けたりする必要があるかどうかを定義します。True に設定されている場合は、WiFi ネットワークに接続されている場合に限り、ユーザーは VoIP 通話を行うことができます。</p>
    <p>既定設定は False です。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP ビデオ用の WiFi が必要</p>
    <p>パラメーター名: <code>RequireWiFiForIPVideo</code></p>
    <p>スコープ: グローバル/サイト/ユーザー</p></td>
    <td><p>この設定では、クライアントが、携帯電話会社の回線ではなく WiFi でビデオ通話を行う必要があるかどうかを定義します。True に設定されている場合は、WiFi ネットワークに接続されている場合に限り、ユーザーはビデオ通話を行うことができます。</p>
    <p>既定設定は False です。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    構成可能なポリシー設定の説明と、ポリシー管理の方法については、「[New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy)」、「[Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy)」、「[Get-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMobilityPolicy)」、「[Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy)」、および「[Remove-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMobilityPolicy)」を参照してください。

  - **エンタープライズ VoIP が有効になっていないユーザーが、クリックして参加を使用して会議に参加できるようにしますか。**
    
    モビリティ機能や勤務先からの通話機能にアクセスできるユーザーは、エンタープライズ VoIP が有効になっている必要があります。しかし、エンタープライズ VoIP が有効になっていないユーザーは、適切な音声ポリシーが割り当てられていれば、モバイル デバイスのリンクをクリックして会議に参加できます。特定の音声ポリシーをこれらのユーザーに割り当てるか、ユーザーに適用されるグローバル ポリシーまたはサイト レベルのポリシーが存在することを確認できます。割り当てた音声ポリシーには、公衆交換電話網 (PSTN) 使用法レコードとユーザーが会議に参加するためにダイヤルできる領域を定義するルートが必要です。音声ポリシー、PSTN 使用法レコード、およびルートの設定の詳細については、「[Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイス ルートの構成](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)」を参照してください。
    
    > [!NOTE]
    > クリックして参加を使用するモバイル ユーザーは、音声ポリシーと、関連する PSTN 使用法レコードおよびボイス ルートが必要です。これは、モバイル デバイス上のリンクをクリックすると、 Lync Server 2013 から発信通話が行われるためです。


## 関連項目

#### 概念

[Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)  

#### その他のリソース

[Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイス ルートの構成](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

