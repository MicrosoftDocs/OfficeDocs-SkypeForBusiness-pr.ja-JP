---
title: Set-CsCertificate で -Roll を使用した音声ビデオおよび OAuth 証明書のステージング
TOCTitle: Set-CsCertificate で -Roll を使用した音声ビデオおよび OAuth 証明書のステージング
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49886875
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsCertificate で -Roll を使用した音声ビデオおよび OAuth 証明書のステージング

 

_**トピックの最終更新日:** 2012-11-13_

音声ビデオ (A/V) 通信は Microsoft Lync Server 2013 の主要コンポーネントです。アプリケーション共有や音声ビデオ会議などの機能では、音声ビデオ エッジ サービス、特に音声ビデオ認証サービスに割り当てられる証明書を利用します。


> [!IMPORTANT]
> <OL>
> <LI>
> <P>この新しい機能は、音声ビデオ エッジ サービスおよび OAuthTokenIssuer 証明書で動作するように作られています。他の証明書の種類を音声ビデオ エッジ サービスおよび OAuth 証明書の種類と共にプロビジョニングすることはできますが、音声ビデオ エッジ サービス証明書のように共存の動作による恩恵を受けることはできません。</P>
> <LI>
> <P>Microsoft Lync Server 2013 の証明書の管理に使用する Lync Server 管理シェルの PowerShell コマンドレットでは、音声ビデオ エッジ サービス証明書を AudioVideoAuthentication 証明書の種類、OAuthServer 証明書を OAuthTokenIssuer 証明書の種類として参照します。このトピックのこれ以降の説明では証明書を一意に識別するために、同じ識別子の種類を使用して AudioVideoAuthentication および OAuthTokenIssuer と呼びます。</P></LI></OL>



音声ビデオ認証サービスは、クライアントやその他の音声ビデオ コンシューマーが使用するトークンを発行する役割を担います。トークンは証明書の属性に基づいて生成されます。証明書の有効期限が切れると接続が失われ、新しい証明書によって生成される新しいトークンを使った再参加が必要になります。Lync Server 2013 の新機能では、この問題が軽減されます。具体的には、古い証明書の有効期限が切れる前に新しい証明書をステージングできるので、両方の証明書を一定期間使い続けることができます。この機能では、Lync Server 管理シェルの Set-CsCertificate コマンドレットの更新された機能を使用します。新しい –Roll パラメーターを既存の –EffectiveDate パラメーターと共に使用すると、新しい AudioVideoAuthentication 証明書が証明書ストアに配置されます。古い方の AudioVideoAuthentication 証明書は、発行済みトークンの照合のためにそのまま残ります。新しい AudioVideoAuthentication 証明書が配置されるのに伴って、次の一連のイベントが発生します。


> [!TIP]
> Lync Server 管理シェルのコマンドレットを証明書の管理に使用すると、エッジ サーバー上の用途ごとに独立した別々の証明書を要求できます。Lync Server 展開ウィザードの証明書ウィザードを利用すると証明書を作成できますが、通常はエッジ サーバーの証明書の用途をすべて 1 つの証明書に結合する<STRONG>既定の</STRONG>種類の証明書が作成されます。ローリング証明書機能を使用する場合は、AudioVideoAuthentication 証明書を他の証明書の用途から切り離すことをお勧めします。既定の種類の証明書をプロビジョニングおよびステージングすることもできますが、結合された証明書の AudioVideoAuthentication 部分のみがステージングによる恩恵を受けます。証明書の有効期限が切れたときに (たとえば) インスタント メッセージングの会話に参加しているユーザーは、アクセス エッジ サービスに関連付けられた新しい証明書を利用するためにいったんログアウトしてログインし直す必要があります。Web 会議エッジ サービスを使用して Web 会議に参加しているユーザーにも同様のことが起こります。OAuthTokenIssuer 証明書は、すべてのサーバーの間で共有される特定の種類の証明書です。証明書を 1 か所で作成して管理し、その証明書が他のすべてのサーバーの中央管理ストアに格納されます。



Set-CsCertificate コマンドレットを使用するとき、および現在の証明書の有効期限が切れる前にこのコマンドレットを使用して証明書をステージングするときのオプションと要件を十分に理解するには、さらに詳しい説明が必要です。重要なのは -Roll パラメーターですが、このパラメーターの用途は実質的に 1 つです。これをパラメーターとして定義する場合は、-Type で定義された、影響を受ける証明書に関する情報 (たとえば AudioVideoAuthentication や OAuthTokenIssuer) と、–EffectiveDate で定義された、証明書が有効になる時期に関する情報を Set-CsCertificate に指定します。

**-Roll:** –Roll パラメーターは必須で、このパラメーターと共に指定する必要がある依存関係を持ちます。どの証明書が影響を受け、どのように適用されるかを完全に定義するための必須パラメーターです。

**-EffectiveDate:** –EffectiveDate パラメーターは、新しい証明書が現在の証明書と共に有効になる時期を定義します。–EffectiveDate は現在の証明書の有効期限の間近に設定することも、それより長い時期に設定することもできます。AudioVideoAuthentication 証明書の場合は、–EffectiveDate を少なくとも 8 時間前に設定することをお勧めします。AudioVideoAuthentication 証明書を使用して発行される音声ビデオ エッジ サービス トークンの既定のトークン存続時間は 8 時間だからです。

OAuthTokenIssuer 証明書をステージングするときは、証明書が有効になるまでのリード タイムの要件が異なります。OAuthTokenIssuer 証明書のリード タイムは、現在の証明書の有効期限が切れる 24 時間以上前に設定する必要があります。共存のリード タイムが長いのは、OAuthTokenIssuer 証明書に依存する他のサーバーの役割 (たとえば Exchange Server) で、証明書によって作成された認証と暗号化キー材料の保有期間が長いためです。

**-Thumbprint:** 拇印は証明書の属性で、証明書ごとに一意となります。–Thumbprint パラメーターを使用して、Set-CsCertificate コマンドレットの処理によって影響を受ける証明書を識別します。

**-Type:** –Type パラメーターは、証明書の 1 つの使用法の種類、またはコンマで区切った証明書の複数の使用法の種類のリストを受け取ることができます。証明書の種類は、その証明書の用途が何かをコマンドレットおよびサーバーに対して明示するものです。たとえば、種類が AudioVideoAuthentication であれば、音声ビデオ エッジ サービスおよび音声ビデオ認証サービスで使用されます。種類の異なる証明書を同時にステージングおよびプロビジョニングする場合は、各証明書に最小限必要な実効リード タイムのうち最も長いものを考慮する必要があります。たとえば、種類が AudioVideoAuthentication と OAuthTokenIssuer の証明書をステージングする必要があるとします。この場合は、2 つの証明書のうち最小限のリード タイムが長い方 (この例では OAuthTokenIssuer) に合わせて –EffectiveDate を設定する必要があります。OAuthTokenIssuer の最小限のリード タイムは 24 時間です。AudioVideoAuthentication 証明書を 24 時間のリード タイムでステージングしたくない場合は、この証明書を別途ステージングし、必要に応じた EffectiveDate を設定します。

## –Roll および -EffectiveDate パラメーターを使用して音声ビデオ エッジ サービス証明書の更新または書き換えを行うには

1.  Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2.  音声ビデオ エッジ サービスの既存の証明書に対するエクスポート可能な秘密キーを使用して、書き換えまたは新しい AudioVideoAuthentication 証明書を要求します。

3.  新しい AudioVideoAuthentication 証明書をエッジ サーバー、およびプール内の他のすべてのエッジ サーバー (プールを展開している場合) にインポートします。

4.  インポートした証明書を Set-CsCertificate コマンドレットで構成し、–Roll パラメーターを –EffectiveDate パラメーターと共に使用します。有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) からトークン存続時間 (既定では 8 時間) を引いた値で定義します。これによって証明書を有効化する時刻が得られるので、–EffectiveDate \<文字列\>: “7/22/2012 6:00:00 AM” のように指定します。
    

    > [!IMPORTANT]
    > エッジ プールでは、最初に展開した証明書の –EffectiveDate パラメーターで定義されている日時までにすべての AudioVideoAuthentication 証明書を展開し、プロビジョニングする必要があります。これは、クライアントとコンシューマーのすべてのトークンが新しい証明書を使って更新される前に、古い証明書の有効期限が切れて音声ビデオ通信が中断するのを防ぐためです。

    
    –Roll および –EffectiveTime パラメーターを使用する Set-CsCertificate コマンドは次のようになります。
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate コマンドの例を次に示します。
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    

    > [!IMPORTANT]
    > EffectiveDate は、サーバーの地域と言語の設定に合った形式にする必要があります。この例で使用している地域と言語の設定は英語 (米国) です。



コンシューマーが使用中の AudioVideoAuthentication を検証するための既存の証明書をそのまま使用しながら、同時に AudioVideoAuthentication の新しいトークンを発行するための新しい証明書をステージングできるように Set-CsCertificate、-Roll、および –EffectiveDate が使用するプロセスを詳しく理解するには、時系列の図を使う方法が効果的です。

次の例では、音声ビデオ エッジ サービス証明書の有効期限が 2012 年 7 月 22 日の午後 2:00 に終了します。管理者は新しい証明書を要求して受け取り、それをプール内の各エッジ サーバーにインポートします。2012 年 7 月 22 日の午前 2:00 に、管理者は –Roll、新しい証明書の拇印文字列に相当する -Thumbprint、および 2012 年 7 月 22 日の午前 6:00 に設定した –EffectiveTime を使用して、Get-CsCertificate の実行を開始します。各エッジ サーバーでこのコマンドを実行します。

![Roll および EffectiveDate パラメーターの使用](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Roll および EffectiveDate パラメーターの使用")

有効時刻 (2012 年 7 月 22 日午前 6:00) になると、新しいトークンはすべて新しい証明書によって発行されます。トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。検証が失敗した場合は、古い証明書が試されます。新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。古い証明書の有効期限が切れた後は (2012 年 7 月 22 日午後 2:00)、トークンは新しい証明書のみを使用して検証されます。古い証明書は、次のように Remove-CsCertificate コマンドレットに –Previous パラメーターを指定して安全に削除できます。

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

## –Roll および -EffectiveDate パラメーターを使用して OAuthTokenIssuer 証明書の更新または書き換えを行うには

1.  Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2.  音声ビデオ エッジ サービスの既存の証明書に対するエクスポート可能な秘密キーを使用して、書き換えまたは新しい OAuthTokenIssuer 証明書を要求します。

3.  新しい OAuthTokenIssuer 証明書をプール内の (プールを展開している場合) フロント エンド サーバーにインポートします。OAuthTokenIssuer 証明書はグローバルにレプリケートされるので、展開内の任意のサーバーで更新および書き換うだけで十分です。ここではフロント エンド サーバーを例に使用しています。

4.  インポートした証明書を Set-CsCertificate コマンドレットで構成し、–Roll パラメーターを –EffectiveDate パラメーターと共に使用します。有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) から少なくとも 24 時間を引いた値で定義します。
    
    –Roll および –EffectiveTime パラメーターを使用する Set-CsCertificate コマンドは次のようになります。
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate コマンドの例を次に示します。
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    

    > [!IMPORTANT]
    > EffectiveDate は、サーバーの地域と言語の設定に合った形式にする必要があります。この例で使用している地域と言語の設定は英語 (米国) です。



有効時刻 (2012 年 7 月 21 日午前 1:00) になると、新しいトークンはすべて新しい証明書によって発行されます。トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。検証が失敗した場合は、古い証明書が試されます。新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。古い証明書の有効期限が切れた後は (2012 年 7 月 22 日午後 2:00)、トークンは新しい証明書のみを使用して検証されます。古い証明書は、次のように Remove-CsCertificate コマンドレットに –Previous パラメーターを指定して安全に削除できます。

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

## 関連項目

#### 概念

[Lync Server 2013 でエッジ サーバー証明書を計画する](lync-server-2013-plan-for-edge-server-certificates.md)  
[Lync Server 2013 でのサーバー間認証 (Oauth) およびパートナー アプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  

#### その他のリソース

[Lync Server 2013 用のエッジ証明書のセットアップ](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)  
[Remove-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCertificate)

