---
title: サーバー間認証証明書を Lync Server 2013 に割り当てる
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06372be3808f3855bc0172cc408308a0c9c9cab2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a>サーバー間認証証明書を Microsoft Lync Server 2013 に割り当てる

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-24_

サーバー間認証証明書が Microsoft Lync Server 2013 に既に割り当てられているかどうかを確認するには、Lync Server 2013 管理シェルから次のコマンドを実行します。

    Get-CsCertificate -Type OAuthTokenIssuer

証明書情報が返されない場合は、サーバー間認証を使用する前に、トークン発行元の証明書を割り当てる必要があります。 一般的な規則として、すべての Lync Server 2013 証明書を OAuthTokenIssuer 証明書として使うことができます。たとえば、Lync Server 2013 の既定の証明書は、OAuthTokenIssuer 証明書としても使うことができます。 (OAUthTokenIssuer 証明書には、[件名] フィールドに SIP ドメイン名を含む Web サーバー証明書でもかまいません)。サーバー間認証に使用される証明書の主な2つの要件を次に示します。 1) 同じ証明書をすべてのフロントエンドサーバー上の OAuthTokenIssuer 証明書として構成する必要があります。および 2) 証明書は、2048ビット以上である必要があります。

サーバー対サーバーの認証に使用できる証明書がない場合は、新しい証明書をインポートして、その証明書をサーバー対サーバーの認証に使用します。 新しい証明書を要求して取得したら、いずれかのフロントエンドサーバーにログオンし、次のような Windows PowerShell コマンドを使用して、その証明書をインポートして割り当てることができます。

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

上記のコマンドパスパラメーターは、証明書ファイルへの完全なパスを表し、Password パラメーターは証明書に割り当てられたパスワードを表します。 この手順は1回だけ実行する必要があります。 Lync Server のレプリケーションサービスは、証明書を解読してすべてのフロントエンドサーバーに展開する一連のスケジュールされたタスクを自動的に作成します。

または、既存の証明書をサーバー間認証証明書として使うこともできます。 (前述のように、既定の証明書をサーバー間認証証明書として使用できます。)次のペアの Windows PowerShell コマンドは、既定の証明書の拇印プロパティの値を取得し、その値を使って、サーバー間認証証明書の既定の証明書を作成します。

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

上のコマンドでは、取得された証明書がグローバルサーバー間認証証明書として機能するように構成されています。これは、証明書がすべてのフロントエンドサーバーにレプリケートされ、使用されることを意味します。 このコマンドは、1つのフロントエンドサーバーでのみ実行できます。 フロントエンドサーバーはすべて同じ証明書を使用する必要がありますが、各フロントエンドサーバーで OAuthTokenIssuer 証明書を構成しないでください。 代わりに、証明書を1回構成して、Lync Server のレプリケーションサーバーがその証明書を各サーバーにコピーできるようにします。

設定-CsCertificate コマンドレットは、該当する証明書を受け取り、現在の OAuthTokenIssuer 証明書として動作するようにその証明書を直ちに構成します。 (Lync Server 2013 では、証明書の種類は、現在の証明書と前の証明書の2つのコピーが保持されます)。新しい証明書を直ちに OAuthTokenIssuer 証明書として使用する必要がある場合は、Set-CsCertificate コマンドレットを使用する必要があります。

Set-CsCertificate コマンドレットを使用して、新しい証明書を "ロール" することもできます。 証明書の "ロール" とは、指定した時点から新しい証明書を現在の OAuthTokenIssuer 証明書にするように構成することを意味します。 たとえば、次のコマンドは、既定の証明書を取得し、2012年7月1日の時点で、現在の OAuthTokenIssuer 証明書としてその証明書を設定するように構成します。

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

2012年7月1日に、新しい証明書は現在の OAuthTokenIssuer 証明書として構成され、"old" OAuthTokenIssuer 証明書は前の証明書として構成されます。

Windows PowerShell を使用しない場合は、[証明書] MMC コンソールを使用して、1つのフロントエンドサーバーから証明書をエクスポートし、その同じ証明書を他のすべてのフロントエンドサーバーにインポートすることもできます。 これを行う場合は、証明書とともに秘密キーを必ずエクスポートしてください。

<div>


> [!WARNING]
> この場合は、各フロントエンドサーバーで手順を実行する必要があります。 この方法で証明書をエクスポートおよびインポートするときに、Lync Server 2013 では、各フロントエンドサーバーに証明書が複製されることはありません。



</div>

証明書がすべてのフロントエンドサーバーにインポートされたら、Windows PowerShell の代わりに Lync Server 展開ウィザードを使用して証明書を割り当てることができます。 展開ウィザードを使用して証明書を割り当てるには、展開ウィザードがインストールされているコンピューターで以下の手順に従います。

1.  [スタート] をクリックし、[すべてのプログラム] をクリックし、[ **Microsoft Lync server 2013**] をクリックして、[ **Lync server Deployment Wizard**] をクリックします。

2.  展開ウィザードで、[ **Lync Server System のインストールまたは更新**] をクリックします。

3.  Microsoft Lync Server 2013 ページで、「**手順 3: 証明書の要求、インストール、または割り当て**を行う」の下にある [**実行**] ボタンをクリックします。 (注: このコンピューターに既に証明書をインストールしている場合は、[**実行**] ボタンは**もう一度 [実行**] というラベルが付けられます。)

4.  証明書ウィザードで、**OAuthTokenIssuer** 証明書を選択してから [**割り当て**] をクリックします。

5.  証明書の割り当てウィザードの [**証明書の割り当て**] ページで、[**次へ**] をクリックします。

6.  [**証明書ストア**] ページで、サーバー対サーバーの認証に使用する証明書を選択して [**次へ**] をクリックします。

7.  [証明書の割り当ての概要] ページで、[**次へ**] をクリックします。

8.  [コマンドを実行しています] ページで、[**完了**] をクリックします。

9.  証明書ウィザードと展開ウィザードを閉じます。

</div>

<span> </span>

</div>

</div>

</div>

