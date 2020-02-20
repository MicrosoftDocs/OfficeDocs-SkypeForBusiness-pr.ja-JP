---
title: Lync Server 2013 へのサーバー間認証証明書の割り当て
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
ms.openlocfilehash: 2d82974f45ab06024f2834609403ed6604067bb2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a>サーバー間認証証明書を Microsoft Lync Server 2013 に割り当てる

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-24_

サーバー間認証証明書が Microsoft Lync Server 2013 に既に割り当てられているかどうかを確認するには、Lync Server 2013 管理シェルから次のコマンドを実行します。

    Get-CsCertificate -Type OAuthTokenIssuer

証明書情報が返されない場合は、サーバー間認証を使用する前に、トークン発行元証明書を割り当てる必要があります。 一般的なルールとして、すべての Lync Server 2013 証明書を OAuthTokenIssuer 証明書として使用できます。たとえば、Lync Server 2013 の既定の証明書を OAuthTokenIssuer 証明書として使用することもできます。 (OAUthTokenIssuer 証明書は、[件名] フィールドに SIP ドメインの名前が含まれる Web サーバー証明書でもかまいません)。サーバー間認証に使用される証明書の主な2つの要件は次のとおりです。 1) すべてのフロントエンドサーバー上の OAuthTokenIssuer 証明書と同じ証明書を構成する必要があります。そして 2) 証明書は、少なくとも2048ビットでなければなりません。

サーバー対サーバーの認証に使用できる証明書がない場合は、新しい証明書をインポートして、その証明書をサーバー対サーバーの認証に使用します。新しい証明書を要求して取得した後で、フロントエンド サーバーのどれかにログオンし、次のような Windows PowerShell コマンドを使用して証明書をインポートして割り当てます。

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

前述のコマンドの Path パラメーターは、証明書ファイルへの完全なパスを表し、Password パラメーターは、その証明書に割り当てられたパスワードを表します。この手順は、1 回だけ実行します。Lync Server のレプリケーション サービスが自動的に作成する一連のスケジュールされたタスクによって、証明書が復号化されてすべてのフロントエンド サーバーに展開されます。

または、既存の証明書をサーバー対サーバーの認証の証明書として使用することもできます (前述したように、既定の証明書をサーバー対サーバーの認証の証明書として使用できます)。次の 2 つの Windows PowerShell コマンドを実行すると、既定の証明書の Thumbprint プロパティの値が取得され、その値を使用して、既定の証明書がサーバー対サーバーの認証の証明書として設定されます。

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

1 つ目のコマンドでは、取得された証明書がグローバルなサーバー対サーバーの認証の証明書として機能するように構成されます。つまり、その証明書はすべてのフロントエンド サーバーにレプリケートされ、使用されます。この場合も、このコマンドはいずれかのフロントエンド サーバーで 1 回だけ実行します。すべてのフロントエンド サーバーで同じ証明書を使用する必要がありますが、各フロントエンド サーバーで OAuthTokenIssuer 証明書を構成する必要はありません。そうではなく、証明書を 1 回構成し、Lync Server のレプリケーション サーバーに各サーバーに対して証明書をコピーさせます。

この証明書を対象とする証明書を取得し、その証明書を現在の OAuthTokenIssuer 証明書として機能するように直ちに設定します。 (Lync Server 2013 は、証明書の種類が現在の証明書と以前の証明書という2つのコピーを保持します。)新しい証明書を OAuthTokenIssuer 証明書としてすぐに機能させる必要がある場合は、コマンドレットを使用する必要があります。

Set-CsCertificate コマンドレットを使用して、新しい証明書を "ロール" することもできます。証明書の "ロール" とは、指定した時点から新しい証明書を現在の OAuthTokenIssuer 証明書にするように構成することを意味します。たとえば、次のコマンドを実行すると、既定の証明書が取得してから、2012 年 7 月 1 日付けでその証明書が現在の OAuthTokenIssuer 証明書になるように構成します。

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

2012 年 7 月 1 日になると、新しい証明書が現在の OAuthTokenIssuer 証明書として構成され、"古い" OAuthTokenIssuer 証明書は以前の証明書として構成されます。

Windows PowerShell を使用したくない場合は、証明書 MMC コンソールを使用して 1 台のフロントエンド サーバーから証明書をエクスポートしてから、同じ証明書を他のすべてのフロントエンド サーバーにインポートします。これを行う場合は、証明書とともに秘密キーを必ずエクスポートしてください。

<div>


> [!WARNING]
> この場合、この手順を各フロントエンド サーバーで実行する必要があります。 この方法で証明書をエクスポートおよびインポートする場合、Lync Server 2013 は各フロントエンドサーバーに証明書をレプリケートしません。



</div>

すべてのフロントエンドサーバーに証明書をインポートした後、その証明書を Windows PowerShell ではなく Lync Server 展開ウィザードを使用して割り当てることができます。 展開ウィザードを使用して証明書を割り当てるには、展開ウィザードがインストールされているコンピューターで以下の手順を実行します。

1.  [スタート]、[すべてのプログラム]、[ **Microsoft Lync server 2013**]、[ **Lync server 展開ウィザード**] の順にクリックします。

2.  展開ウィザードで、[**Lync Server システムのインストールまたは更新**] をクリックします。

3.  [Microsoft Lync Server 2013] ページで、[**ステップ 3: 証明書の要求、インストール、または割り当て**] の下にある [**実行**] ボタンをクリックします。 (メモ: このコンピューターに既に証明書をインストールしている場合は、[**実行**] ボタンに [**再実行**] と表示されます。)

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

