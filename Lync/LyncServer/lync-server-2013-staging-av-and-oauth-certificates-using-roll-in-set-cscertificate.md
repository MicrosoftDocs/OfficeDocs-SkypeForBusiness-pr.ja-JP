---
title: 設定-CsCertificate での、AV および OAuth 証明書の使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 583ab13e50cac7c7a8b345a2ea2cf4c4e1e38d7f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Lync Server 2013 での、AV および OAuth 証明書の使用-セットアップ-CsCertificate

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-13_

音声/ビデオ (A/V) 通信は、Microsoft Lync Server 2013 の主要コンポーネントです。 アプリケーション共有、音声会議、ビデオ会議などの機能は、A/v Edge サービスに割り当てられている証明書、特に A/V 認証サービスに依存しています。

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>この新機能は、A/V Edge サービスと<EM>Oauthtokenissuer</EM>証明書で動作するように設計されています。 その他の種類の証明書は、A/V Edge サービスと OAuth 証明書の種類と共にプロビジョニングできますが、A/V Edge サービス証明書の共存動作の恩恵を受けることはできません。</P>
> <LI>
> <P>Microsoft Lync Server 2013 証明書を管理するために使用される Lync Server 管理シェル PowerShell コマンドレットは、 <EM>Audiovideoauthentication</EM>証明書の種類としての A/V Edge サービス証明書と、Type <EM>Oauthtokenissuer</EM>としての oauthserver certificate を指します。 このトピックのこれ以降の説明では証明書を一意に識別するために、同じ識別子の種類を使用して <EM>AudioVideoAuthentication</EM> および <EM>OAuthTokenIssuer</EM> と呼びます。</P></LI></OL>



</div>

A/V 認証サービスは、クライアントや他の A/V コンシューマーによって使用されるトークンの発行を担当します。 トークンは証明書の属性から生成され、証明書の有効期限が切れたときに、新しい証明書によって生成された新しいトークンに接続を切断して、もう一度参加するための要件があります。 Lync Server 2013 の新機能により、古い証明書を前もって古いものから事前にステージングし、両方の証明書を一定期間有効にすることができます。 この機能では、Set-CsCertificate Lync Server Management Shell コマンドレットの更新された機能を使用します。 新しいパラメーター– Roll は既存のパラメーター– EffectiveDate を使用して、新しい AudioVideoAuthentication 証明書を証明書ストアに配置します。 以前の AudioVideoAuthentication 証明書は、確認のために発行されたトークンのまま残ります。 新しい AudioVideoAuthentication 証明書を所定の場所に配置すると、次の一連のイベントが発生します。

<div>


> [!TIP]
> Lync Server Management Shell コマンドレットを使用して、証明書を管理するために、エッジサーバー上の各目的に対して個別の証明書を要求できます。 Lync Server 展開ウィザードの [証明書] ウィザードを使用すると、証明書を作成できますが、通常は、エッジサーバーで使用されるすべての証明書を1つの証明書に結合する<STRONG>既定</STRONG>の種類があります。 ローリング証明書機能を使用する場合は、AudioVideoAuthentication 証明書を他の証明書の用途から切り離すことをお勧めします。 既定の種類の証明書をプロビジョニングおよびステージングすることもできますが、結合された証明書の AudioVideoAuthentication 部分のみがステージングによる恩恵を受けます。 ユーザー (たとえば、証明書の有効期限が切れたときのインスタントメッセージの会話) では、アクセスエッジサービスに関連付けられた新しい証明書を使用するためにログアウトしてもう一度ログインする必要があります。 Web 会議エッジサービスを使って Web 会議に参加しているユーザーに対しても同様の動作が発生します。 OAuthTokenIssuer 証明書は、すべてのサーバーの間で共有される特定の種類の証明書です。 証明書を1か所で作成して管理すると、その証明書は、他のすべてのサーバーの中央管理ストアに保存されます。



</div>

Set-CsCertificate コマンドレットを使用するとき、および現在の証明書の有効期限が切れる前にこのコマンドレットを使用して証明書をステージングするときのオプションと要件を十分に理解するには、さらに詳しい説明が必要です。重要なのは -Roll パラメーターですが、このパラメーターの用途は実質的に 1 つです。これをパラメーターとして定義する場合は、-Type で定義された、影響を受ける証明書に関する情報 (たとえば AudioVideoAuthentication や OAuthTokenIssuer) と、-EffectiveDate で定義された、証明書が有効になる時期に関する情報を Set-CsCertificate に指定します。

**-ロール:**–ロールパラメーターは必須であり、同時に指定する必要がある依存関係がある必要があります。 どの証明書が影響を受け、どのように適用されるかを完全に定義するための必須パラメーターです。

**-EffectiveDate:** パラメーター– EffectiveDate は、新しい証明書が現在の証明書で相互に相互にアクティブになるタイミングを定義します。 – EffectiveDate は、現在の証明書の有効期限が近づいているか、または長い時間が経過している可能性があります。 AudioVideoAuthentication certificate の推奨最小– EffectiveDate は8時間で、AudioVideoAuthentication certificate を使って発行される AV Edge サービストークンの既定のトークンの有効期間です。

OAuthTokenIssuer 証明書をステージングするときは、証明書が有効になるまでのリード タイムの要件が異なります。OAuthTokenIssuer 証明書のリード タイムは、現在の証明書の有効期限が切れる 24 時間以上前に設定する必要があります。共存のリード タイムが長いのは、OAuthTokenIssuer 証明書に依存する他のサーバーの役割 (たとえば Exchange Server) で、証明書によって作成された認証と暗号化キー材料の保有期間が長いためです。

**-拇印:** 拇印は、その証明書に固有の証明書の属性です。 -Thumbprint パラメーターを使用して、Set-CsCertificate コマンドレットの処理によって影響を受ける証明書を識別します。

**-Type:**–型パラメーターは、1つの証明書の使用の種類を受け付けることができます。または、証明書の使用の種類のコンマ区切りリストを指定します。 証明書の種類は、コマンドレットに対して識別するものであり、証明書の目的はサーバーに対して指定されています。 たとえば、「AudioVideoAuthentication」と入力すると、A/V Edge サービスと AV 認証サービスが使用されます。 異なる種類の証明書を同時にステージングおよびプロビジョニングすることにした場合は、証明書に必要な最も長い最小のリードタイムを考慮する必要があります。 たとえば、AudioVideoAuthentication と OAuthTokenIssuer の証明書をステージする必要があります。 少なくとも EffectiveDate は、この2つの証明書の大部分である必要があります。この例では、最小のリード時間が24時間である OAuthTokenIssuer です。 オーディオビデオ認証証明書のステージが24時間の間にない場合は、要件により多くの EffectiveDate と個別にステージを整理します。

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>–ロールと-EffectiveDate のパラメーターを使用して A/V エッジサービス証明書を更新または更新するには

1.  Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2.  A/V Edge サービス上の既存の証明書のエクスポート可能な秘密キーを使って、更新または新しい AudioVideoAuthentication 証明書を要求します。

3.  新しい AudioVideoAuthentication 証明書を、エッジサーバーとプール内の他のすべてのエッジサーバーにインポートします (プールが展開されている場合)。

4.  インポートした証明書を Set-CsCertificate コマンドレットで構成し、-Roll パラメーターを -EffectiveDate パラメーターと共に使用します。 有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) からトークン存続時間 (既定では 8 時間) を引いた値で定義します。 これにより、証明書がアクティブに設定されている必要があり、– \<EffectiveDate\>STRING: "7/22/2012 6:00:00 AM" のようになります。
    
    <div>
    

    > [!IMPORTANT]
    > エッジプールの場合、すべてのクライアントとコンシューマーのトークンが新しい証明書を使用して更新される前に、古い証明書の EffectiveDate パラメーターで定義された日付と時刻で、すべての AudioVideoAuthentication 証明書を展開してプロビジョニングする必要があります。

    
    </div>
    
    -Roll および -EffectiveTime パラメーターを使用する Set-CsCertificate コマンドは次のようになります。
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate コマンドの例を次に示します。
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > EffectiveDate は、サーバーの地域と言語の設定に合った形式にする必要があります。この例で使用している地域と言語の設定は英語 (米国) です。

    
    </div>

コンシューマーが使用中の AudioVideoAuthentication を検証するための既存の証明書をそのまま使用しながら、同時に AudioVideoAuthentication の新しいトークンを発行するための新しい証明書をステージングできるように Set-CsCertificate、-Roll、および -EffectiveDate が使用するプロセスを詳しく理解するには、時系列の図を使う方法が効果的です。

次の例では、管理者は、A/V Edge サービス証明書が07/22/2012 の 2:00:00 PM に有効期限切れになっていることを確認します。 彼は、新しい証明書を要求して受け取り、その証明書を自分のプールの各エッジサーバーにインポートします。 07/22/2012 の午前2時は、[ロール]、[拇印] が新しい証明書の拇印文字列と同じであり、-EffectiveTime が 07/22/2012 6:00:00 AM に設定されている Get-CsCertificate の実行を開始します。 各エッジサーバーでこのコマンドを実行します。

![Roll および EffectiveDate パラメーターの使用](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Roll および EffectiveDate パラメーターの使用")

有効時間 (7/22/2012 6:00:00 AM) に達すると、新しい証明書によってすべての新しいトークンが発行されます。 トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。 検証が失敗した場合は、古い証明書が試されます。 新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。 古い証明書の有効期限が切れた後 (7/22/2012 2:00:00 PM)、トークンは新しい証明書でのみ検証されます。 古い証明書は、次のように Remove-CsCertificate コマンドレットに -Previous パラメーターを指定して安全に削除できます。

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>–ロールと-EffectiveDate のパラメーターを使用して OAuthTokenIssuer 証明書を更新または更新するには

1.  Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2.  A/V Edge サービス上の既存の証明書のエクスポート可能な秘密キーを使用して、更新または新しい OAuthTokenIssuer 証明書を要求します。

3.  新しい OAuthTokenIssuer 証明書を、プールのフロントエンドサーバーにインポートします (プールが展開されている場合)。 OAuthTokenIssuer 証明書はグローバルにレプリケートされるので、展開内の任意のサーバーで更新と書き換えを行うだけで十分です。 フロントエンドサーバーは例として使用されます。

4.  インポートした証明書を Set-CsCertificate コマンドレットで構成し、-Roll パラメーターを -EffectiveDate パラメーターと共に使用します。有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) から少なくとも 24 時間を引いた値で定義します。
    
    -Roll および -EffectiveTime パラメーターを使用する Set-CsCertificate コマンドは次のようになります。
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate コマンドの例を次に示します。
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > EffectiveDate は、サーバーの地域と言語の設定に合った形式にする必要があります。この例で使用している地域と言語の設定は英語 (米国) です。

    
    </div>

有効時間 (7/21/2012 1:00:00 AM) に達すると、新しい証明書によってすべての新しいトークンが発行されます。 トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。 検証が失敗した場合は、古い証明書が試されます。 新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。 古い証明書の有効期限が切れた後 (7/22/2012 2:00:00 PM)、トークンは新しい証明書でのみ検証されます。 古い証明書は、次のように Remove-CsCertificate コマンドレットに -Previous パラメーターを指定して安全に削除できます。

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でエッジ サーバー証明書を計画する](lync-server-2013-plan-for-edge-server-certificates.md)  
[Lync Server 2013 でのサーバー間認証 (OAuth) とパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[Lync Server 2013 用のエッジ証明書のセットアップ](lync-server-2013-set-up-edge-certificates.md)  
[設定-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))  
[CsCertificate の削除](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

