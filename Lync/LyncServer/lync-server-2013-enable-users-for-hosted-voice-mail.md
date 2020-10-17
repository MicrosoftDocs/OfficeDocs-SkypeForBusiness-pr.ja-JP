---
title: 'Lync Server 2013: ホストボイスメールに対してユーザーを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c0975f6be3d78ec7634859b26e7ed35e7efee5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501034"
---
# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Lync Server 2013 でホストボイスメールに対してユーザーを有効にする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-24_

手順に従い、hosted Exchange ユニファイドメッセージング (UM) サービスで Lync Server 2013 ユーザーのボイスメールを有効にします。

詳細については、「計画」のドキュメントの「 [Hosted Exchange user management In Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) 」を参照してください。

[Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)コマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。

<div>


> [!IMPORTANT]  
> ホストボイスメールに対して Lync Server 2013 ユーザーを有効にするには、そのユーザーアカウントに適用するホストボイスメールポリシーを展開する必要があります。 詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホストボイスメールポリシー</A>」を参照してください。



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>ホストボイスメールに対してユーザーを有効にするには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  Set-CsUser コマンドレットを実行して、ホストボイスメールのユーザーアカウントを構成します。 たとえば、以下を実行します。
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    上述の例では、次のパラメーターが設定されます。
    
      - **HostedVoiceMail** では、ユーザーのボイスメール呼び出しを、ホストされた Exchange UM にルーティングすることができます。 また、Microsoft Lync 2013 に通知して、"ボイスメールの呼び出し" インジケーターを明るくします。
    
      - **Identity** により、変更するユーザー アカウントを指定しています。 Identity 値は、以下の形式のいずれかで指定できます。
        
          - ユーザーの SIP アドレス
        
          - ユーザーの Active Directory ユーザー プリンシパル名
        
          - ユーザーのドメイン \\ ログオン名 (たとえば、contoso \\ kenmyer)
        
          - ユーザーの Active Directory ドメイン サービス表示名 (例: Ken Myer)。 Display-Name を Identity 値として使用する場合は、アスタリスク ( \* ) ワイルドカード文字を使用できます。 たとえば、"smith" という Id は、" \* smith" という文字列値で終わる Display-Name を持つすべてのユーザーを返します。
        
        <div>
        

        > [!NOTE]  
        > ユーザーの Active Directory SAM アカウント名は、フォレスト内で一意の名前とは限らないため、Identity 値として使用することはできません。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

