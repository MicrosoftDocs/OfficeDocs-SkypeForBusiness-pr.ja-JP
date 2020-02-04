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
ms.openlocfilehash: c69f7a5b32b4ad0dd31f8be118aa2f2173ff3e22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>Lync Server 2013 でのカスタムプレゼンス状態の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-10_

Lync 2013 でカスタムプレゼンス状態を定義するには、XML カスタムプレゼンス構成ファイルを作成して、Lync Server 管理シェルコマンドレットで、**新しい CSClientPolicy**を使用するか、またはパラメーター CustomStateURL を**設定**して、その場所を指定します。

構成ファイルには、次のプロパティがあります。

  - カスタムプレゼンス状態は、[利用可能]、[取り込み中]、[応答不可] のプレゼンスインジケーターで構成できます。

  - [可用性] 属性は、カスタム状態の状態テキストに関連付けられているプレゼンスインジケーターを決定します。 このトピックの後半の例では、[自宅から] の状態テキストが緑色 (使用可能) のプレゼンスインジケーターの右側に表示されています。

  - 状態テキストの最大の長さは、64文字です。

  - 最大4つのカスタムプレゼンス状態を追加できます。

  - CustomStateURL パラメーターは、構成ファイルの場所を指定します。 Lync 2013 では、SIP high security モードは既定で有効になっているため、HTTPS が有効になっている web サーバーにカスタムのプレゼンス設定ファイルを格納する必要があります。 そうしないと、Lync 2013 クライアントに接続できなくなります。 たとえば、有効なアドレスになり`https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`ます。

<div>


> [!NOTE]  
> 実稼働環境ではお勧めできませんが、HTTPS 以外のファイル共有に配置されている構成ファイルをテストするには、EnableSIPHighSecurityMode registry 設定を使用して、クライアントで SIP high security モードを無効にします。 次に、CustomStateURL レジストリ設定を使用して、構成ファイルの HTTPS 以外の場所を指定できます。 Lync 2013 では Lync 2010 のレジストリ設定は無視されますが、レジストリハイブは更新されています。 レジストリ設定は次の手順で作成します。 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>Type: DWORD</P>
> <P>値のデータ: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>Type: String (REG_SZ)</P>
> <P>値のデータ (例):\\File://lspool または file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</P></LI></UL>



</div>

XML 構成ファイルで1つ以上のロケール ID (LCID) スキーマを指定して、カスタムのプレゼンス状態をローカライズします。 このトピックの後半の例では、ローカライズされた言語 (1033)、ノルウェー語-ブークモール (1044)、フランス語-フランス (1036)、およびトルコ語 (1055) について説明します。 Lcid の一覧については、「Microsoft によって<http://go.microsoft.com/fwlink/p/?linkid=157331>割り当てられたロケール id」をご覧ください。

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a>Lync 2013 にカスタムプレゼンス状態を追加するには

1.  次の例の形式を使用する XML 構成ファイルを作成します。
    
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

2.  HTTPS が有効になっている web サーバーに XML 構成ファイルを保存します。 この例では、ファイルには ".xml" という名前が付けhttps://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xmlられ、場所に保存されています。

3.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

4.  Lync Server 管理シェルで、次のようなコマンドを使用して、XML 構成ファイルの場所を定義します。
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  この新しいポリシーをユーザーに割り当てるには、**グラント Clientpolicy**コマンドレットを使用します。

詳細については、「[新しい-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) 」と「Lync Server 管理シェルドキュメントの[権限を付与](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy)する」を参照してください。

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>既定では、Lync Server&nbsp;2013 は、クライアントポリシーと設定を3時間ごとに更新します。</P>
> <LI>
> <P>CustomStateURL などの以前のリリースのグループポリシー設定を引き続き使用する場合、Lync 2013 は、その設定が新しいポリシーレジストリハイブ (HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync) にある場合にその設定を認識します。 ただし、サーバーベースのクライアントポリシーが優先されます。</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

