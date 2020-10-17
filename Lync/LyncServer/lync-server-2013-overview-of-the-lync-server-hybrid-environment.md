---
title: 'Lync Server 2013: Lync Server ハイブリッド環境の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99aeda6136c79b7ffda9b5cd3d5dced3b1f6ee4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516114"
---
# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Lync Server 2013 ハイブリッド環境の概要

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-28_

Lync Server 2013 ハイブリッド環境とは、オンプレミスの Lync Server 2013 に所属するユーザーや、Lync Online に所属している他のユーザーが、user@contoso.com などの同じドメインを共有する展開のことを指します。

<div>

## <a name="about-this-guide"></a>このガイドについて

このガイドでは、lync Online との相互運用性を実現するために Lync Server 2013 環境を構成し、オンプレミス展開から Lync Online を使用するようにユーザーを移動するために必要なタスクについて説明します。

</div>

<div>

## <a name="prerequisites"></a>必要条件

ハイブリッド展開を構成するためのタスクを完了するには、次のアプリケーションとユーティリティがインストールされている必要があります。 これらのファイルのインストーラーは、展開で提供されるインストールメディアと、次の一覧に含まれているリンクに含まれています。

  - [Active Directory フェデレーション サービス (AD FS) 2.0](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Microsoft ディレクトリ同期ツール9.1](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [AD FS を使用したシングルサインオン用の Windows PowerShell のインストール](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - Microsoft Online Services サインインアシスタント (msoidcli-7.0.msi) は、microsoft 365 のデスクトップセットアップに含まれています。これは、Microsoft 365 管理センターからリンクされているダウンロードページから入手できます。

</div>

<div>

## <a name="administrator-credentials"></a>管理者の資格情報

管理者の資格情報を入力するように求めるメッセージが表示されたら、Microsoft 365 または Office 365 組織の管理者アカウントのユーザー名とパスワードを使用します。 Active Directory フェデレーションサービス (AD FS) 2.0、ディレクトリ同期、シングルサインオン、フェデレーション、および Lync Online へのユーザーの移動を構成するときに、これらの資格情報を使用することもできます。

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>Lync Online PowerShell への接続

管理者は、Windows PowerShell を使用して Lync Online と Lync Online ユーザーアカウントを管理できるようになりました。 これを行うには、まず、Microsoft ダウンロードセンター (から Lync Online Connector モジュールをダウンロードしてインストールする必要があり https://go.microsoft.com/fwlink/?LinkId=294688) ます。 Lync Online コネクタモジュールをダウンロード、インストール、および使用する方法、および Windows PowerShell を使用して Lync Online を管理する方法の詳細については、「 [Windows powershell を使用して Lync online を管理する](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

