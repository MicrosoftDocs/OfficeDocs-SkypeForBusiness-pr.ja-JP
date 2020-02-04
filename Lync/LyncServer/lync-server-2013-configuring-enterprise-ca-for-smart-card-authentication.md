---
title: 'Lync Server 2013: スマートカード認証用のエンタープライズ CA の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44df62031e679c641b4c7dbe6b5c205e1ae899e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>Lync Server 2013 でのスマートカード認証用のエンタープライズ CA の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-03_

以下のセクションでは、スマートカード認証をサポートするようにエンタープライズのルート証明機関 (CA) を構成する方法について説明します。 エンタープライズルート CA をインストールする方法については、「エンタープライズルート証明機関をインストール[http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)する」を参照してください。

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>スマートカード認証をサポートするようにエンタープライズルート証明機関を構成する

スマート カード認証をサポートするようにエンタープライズ ルート CA を構成する方法を以下の手順で説明します。

1.  ドメイン管理者のアカウントを使用してエンタープライズ CA コンピューターにログインします。

2.  システム マネージャーを起動し、証明機関 Web 登録の役割がインストールされていることを確認します。

3.  [**管理ツール**] メニューから**証明機関**管理コンソールを開きます。

4.  ナビゲーション ウィンドウで、[**証明機関**] を展開します。

5.  [**証明書テンプレート**] を右クリックし、[**新規作成**] をクリックして、[**発行する証明書テンプレート**] を選択します。

6.  [**登録エージェント**]、[**スマート カード ユーザー**]、[**スマート カード ログオン**] の順にクリックします。

7.  [**OK**] をクリックします。

8.  [**証明書テンプレート**] を右クリックします。

9.  [**管理**] を選択します。

10. スマート カード ユーザー テンプレートのプロパティを開きます。

11. [**セキュリティ**] タブをクリックします。

12. アクセス許可を次のように変更します。
    
      - 読み取り/登録 (許可) アクセス許可を指定して個別のユーザー AD アカウントを追加します。または
    
      - 読み取り/登録 (許可) のアクセス許可を指定してスマート カード ユーザーを含むセキュリティ グループを追加します。または
    
      - 読み取り/登録 (許可) のアクセス許可を指定してドメイン ユーザー グループを追加します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

