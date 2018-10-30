---
title: カスタム プレゼンス状態の構成
TOCTitle: カスタム プレゼンス状態の構成
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398997(v=OCS.15)
ms:contentKeyID: 52056733
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# カスタム プレゼンス状態の構成

 

_**トピックの最終更新日:** 2016-12-08_

Lync 2013 でカスタム プレゼンス状態を定義するには、XML カスタム プレゼンス構成ファイルを作成してから、Lync Server 管理シェルのコマンドレット **New-CSClientPolicy** または **Set-CSClientPolicy** とパラメーター CustomStateURL を使用して、構成ファイルの場所を指定します。

構成ファイルには次のプロパティがあります。

  - 連絡可能、取り込み中、応答不可といったプレゼンス インジケーターを使用して、カスタム プレゼンス状態を構成できます。

  - 状態属性は、どのプレゼンス インジケーターがカスタム状態の状態テキストに関連付けられているかを示します。 このトピックで後述する例では、緑色 (連絡可能) プレゼンス インジケーターの右側に、状態テキスト \[自宅で仕事中\] が表示されます。

  - 状態テキストの最大文字数は 64 文字です。

  - 最大で 4 つのカスタム プレゼンス状態を追加できます。

  - CustomStateURL パラメーターは構成ファイルの場所を指定します。Lync 2013 では、SIP 高セキュリティ モードは既定で有効です。このことにより、HTTPS を有効にした Web サーバーにカスタムのプレゼンス構成ファイルを格納する必要があります。このようにしないと、Lync 2013 クライアントは接続することができません。たとえば、有効なアドレスは `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml` のようになります。

> [!NOTE]  
> 運用環境では推奨されませんが、クライアントで SIP 高セキュリティ モードを無効にする目的で EnableSIPHighSecurityMode レジストリ設定を使用して、非 HTTPS のファイル共有にある構成ファイルをテストできます。次に、CustomStateURL レジストリ設定を使用して、非 HTTPS での構成ファイルの場所を指定できます。Lync 2013 では Lync 2010 のレジストリ設定は有効ですが、レジストリ ハイブが更新されていることに注意してください。レジストリ設定は以下のように作成します。
> <ul><li><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</p>
> <p>種類: DWORD</p>
> <p>値のデータ: 0</p></li>
> <li><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</p>
> <p>種類: 文字列 (REG_SZ)</p>
> <p>値のデータ (例): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</p></li>
> </ul>


XML 構成ファイルに 1 つまたは複数のロケール ID (LCID) スキーマを指定して、カスタム プレゼンス状態をローカライズします。このトピックで後述する例では、英語 - 米国 (1033)、ノルウェー語 - ブークモール (1044)、フランス語 - フランス (1036)、およびトルコ語 (1055) へのローカリゼーションを示します。LCID の一覧については、<http://go.microsoft.com/fwlink/?linkid=157331>にアクセスし、Microsoft によって割り当てられているロケール ID を参照してください。

## カスタム プレゼンス状態を Lync 2013 に追加するには

1.  次の例のフォーマットを使用して、XML 構成ファイルを作成します。
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  HTTPS が有効な Web サーバーに XML 構成ファイルを保存します。この例では、ファイルは Presence.xml の名前で、https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml に保存されます。

3.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

4.  Lync Server 管理シェルで、次のようなコマンドを使用して、XML 構成ファイルの場所を定義します。
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  **Grant-CSClientPolicy** コマンドレットを使用して、この新しいポリシーをユーザーに割り当てます。

詳細については、「Lync Server 管理シェル」のドキュメントの「[New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy)」と「[Grant-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientPolicy)」を参照してください。

> [!NOTE]  
> <ul><li><p>既定では、Lync Server 2013 でクライアント ポリシーと設定が 3 時間ごとに更新されます。</p></li>
> <li><p>CustomStateURL のような、以前の製品リリースからのグループ ポリシー設定を引き続き使用する必要がある場合、これらが新しいポリシー レジストリ ハイブ (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync) にあれば、Lync 2013 はこの設定を認識します。ただし、サーバーベースのクライアント ポリシーが優先されます。</p></li>
> </ul>

