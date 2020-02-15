---
title: 'Lync Server 2013: カスタムプレゼンス状態の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75e2e47af4951e98f21ea6b26572d39b5eebcb8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>Lync Server 2013 でのカスタムプレゼンス状態の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-10_

Lync 2013 でカスタムプレゼンス状態を定義するには、XML カスタムプレゼンス構成ファイルを作成し、Lync Server 管理**シェルコマンドレット**を使用してその場所を指定する**か、** またはパラメーター customstateurl を使用して、その場所を指定します。

構成ファイルには、次のプロパティがあります。

  - カスタムプレゼンス状態は、[利用可能]、[取り込み中]、[応答不可] のプレゼンスインジケーターで構成できます。

  - Availability 属性は、カスタム状態の状態テキストに関連付けられているプレゼンスインジケーターを決定します。 このトピックの後半の例では、自宅から作業中の状態テキストが緑の (利用可能な) プレゼンスインジケーターの右側に表示されます。

  - 状態テキストの最大長は64文字です。

  - 最大4つのカスタムプレゼンス状態を追加できます。

  - CustomStateURL パラメーターは、構成ファイルの場所を指定します。 Lync 2013 では、SIP 高セキュリティモードが既定で有効になっているので、HTTPS が有効になっている web サーバーにカスタムプレゼンス構成ファイルを格納する必要があります。 それ以外の場合、Lync 2013 クライアントは接続できなくなります。 たとえば、有効なアドレスはになり`https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`ます。

<div>


> [!NOTE]  
> 運用環境では推奨されていませんが、EnableSIPHighSecurityMode レジストリ設定を使用してクライアントの SIP 高セキュリティモードを無効にすることにより、HTTPS 以外のファイル共有にある構成ファイルをテストできます。 その後、CustomStateURL レジストリ設定を使用して、構成ファイルの HTTPS 以外の場所を指定できます。 Lync 2013 は Lync 2010 レジストリ設定を受け入れますが、レジストリハイブは更新されていることに注意してください。 レジストリ設定は次のように作成します。 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>型: DWORD</P>
> <P>値のデータ: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>型: String (REG_SZ)</P>
> <P>値のデータ (例):\\file://lspool com\LSFileShare\ClientConfigFolder\Presence.xml または file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</P></LI></UL>



</div>

XML 構成ファイルで1つまたは複数のロケール ID (LCID) スキーマを指定して、カスタムプレゼンス状態をローカライズします。 このトピックの後半の例では、英語-米国 (1033)、ノルウェー語 (1044)、フランス語-フランス (1036)、トルコ語 (1055) にローカライズされています。 Lcid の一覧については、「Microsoft が割り当てた<http://go.microsoft.com/fwlink/p/?linkid=157331>ロケール id」を参照してください。

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a>カスタムプレゼンス状態を Lync 2013 に追加するには

1.  次の例の形式を使用して、XML 構成ファイルを作成します。
    
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

2.  XML 構成ファイルを HTTPS が有効になっている web サーバーに保存します。 この例では、ファイルには「xml」という名前が付けhttps://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xmlられ、場所に保存されます。

3.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

4.  Lync Server 管理シェルで、次のようなコマンドを使用して、XML 構成ファイルの場所を定義します。
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  この新しいポリシーをユーザーに割り当てるには、 **Grant-CSClientPolicy**コマンドレットを使用します。

詳細については、「Lync Server Management Shell」のドキュメントの「 [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) 」および「 [Grant-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) 」を参照してください。

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>既定では、Lync Server&nbsp;2013 は3時間ごとにクライアントポリシーと設定を更新します。</P>
> <LI>
> <P>CustomStateURL などの以前のリリースからのグループポリシー設定を引き続き使用する場合、Lync 2013 は、その設定が新しいポリシーレジストリハイブ (HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync) にある場合に、その設定を認識します。 ただし、サーバーベースのクライアントポリシーは優先されます。</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

