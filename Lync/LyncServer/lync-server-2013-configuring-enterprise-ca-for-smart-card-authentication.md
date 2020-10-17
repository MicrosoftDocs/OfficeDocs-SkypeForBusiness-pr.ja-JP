---
title: 'Lync Server 2013: スマートカード認証用にエンタープライズ CA を構成する'
description: 'Lync Server 2013: スマートカード認証用にエンタープライズ CA を構成する。'
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
ms.openlocfilehash: 98044c96dd04d02fd87609918f309cf65227b133
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548443"
---
# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>Lync Server 2013 でのスマートカード認証のエンタープライズ CA の構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-03_

次のセクションでは、スマートカード認証をサポートするようにエンタープライズのルート証明機関 (CA) を構成する方法について説明します。 エンタープライズルート CA のインストール方法については、「エンタープライズのルート証明機関をインストールする」を参照してください [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) 。

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>スマートカード認証をサポートするようにエンタープライズルート証明機関を構成する

次の手順では、スマートカード認証をサポートするようにエンタープライズルート CA を構成する方法について説明します。

1.  ドメイン管理者アカウントを使用して、エンタープライズ CA コンピューターにログインします。

2.  システムマネージャーを起動し、証明機関 Web 登録役割がインストールされていることを確認します。

3.  [ **管理ツール** ] メニューから、 **証明機関** 管理コンソールを開きます。

4.  ナビゲーションウィンドウで、[ **証明機関**] を展開します。

5.  [ **証明書テンプレート**] を右クリックし、[ **新規作成**] を選択して、[ **発行する証明書テンプレート**] を選択します。

6.  [ **登録エージェント**]、[ **スマートカードユーザー**]、および [ **スマートカードログオン**] を選択します。

7.  **[OK]** をクリックします。

8.  [ **証明書テンプレート**] を右クリックします。

9.  [ **管理**] を選択します。

10. スマートカードユーザーテンプレートのプロパティを開きます。

11. [ **セキュリティ** ] タブをクリックします。

12. アクセス許可を次のように変更します。
    
      - 読み取り/登録 (許可) のアクセス許可を持つ個々のユーザー AD アカウントを追加するか、または
    
      - 読み取り/登録 (許可) のアクセス許可を持つスマートカードユーザーを含むセキュリティグループを追加するか、または
    
      - 読み取り/登録 (許可) のアクセス許可を持つドメインユーザーグループを追加する

</div>

</div>

<span> </span>

</div>

</div>

</div>

