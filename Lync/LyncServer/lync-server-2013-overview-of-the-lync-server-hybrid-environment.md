---
title: 'Lync Server 2013: Lync Server のハイブリッド環境の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0420e4aaded9f5ae90d26c4cbdc176e7fb4c6bb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Lync Server 2013 ハイブリッド環境の概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-28_

Lync Server 2013 ハイブリッド環境とは、オンプレミスの Lync Server 2013 およびその他のユーザーが Lync Online に接続しているが、ユーザーが user@contoso.com などの同じドメインを共有している展開を指します。

<div>

## <a name="about-this-guide"></a>このガイドについて

このガイドでは、lync Online との相互運用性を確保するために Lync Server 2013 環境を構成するために必要なタスクについて説明し、ユーザーをオンプレミスの展開から Lync Online を使用するように移動するために必要な作業について説明します

</div>

<div>

## <a name="prerequisites"></a>前提条件

ハイブリッド展開を構成するためのタスクを実行するには、次のアプリケーションとユーティリティがインストールされている必要があります。 これらのファイルのインストーラーは、展開用に提供されているインストールメディアと、次の一覧に記載されているリンクに含まれています。

  - [Active Directory フェデレーションサービス (AD FS) 2.0](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Microsoft ディレクトリ同期ツール9.1](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [AD FS を使ってシングルサインオン用に Windows PowerShell をインストールする](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - Microsoft Online Services サインインアシスタント (msoidcli-) は、office 365 のデスクトップセットアップに含まれています。 office 365 管理ポータルからリンクされたダウンロードページから入手できます。

</div>

<div>

## <a name="administrator-credentials"></a>管理者の資格情報

管理者の資格情報を入力するように求められたら、Office 365 テナントの管理者アカウントのユーザー名とパスワードを使用します。 Active Directory フェデレーションサービス (AD FS) の2.0、ディレクトリ同期、シングルサインオン、フェデレーション、ユーザーの Lync Online への移動を構成するときにも、これらの資格情報を使います。

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>Lync Online PowerShell への接続

管理者は、Windows PowerShell を使用して Lync Online と Lync Online のユーザーアカウントを管理することができるようになりました。 そのためには、まず Microsoft ダウンロードセンター (http://go.microsoft.com/fwlink/?LinkId=294688)) から Lync Online Connector モジュールをダウンロードしてインストールする必要があります。 Lync Online Connector モジュールのダウンロード、インストール、および使用の詳細と Windows PowerShell を使用して Lync Online を管理する方法の詳細については、「 [Windows Powershell を使用して Lync online を管理する](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

