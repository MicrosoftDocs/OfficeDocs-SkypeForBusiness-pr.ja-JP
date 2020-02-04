---
title: WMI の下位互換性パッケージをインストールする
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c3b8d474ff451a488124ebfbae0ff0872a6cca1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>WMI の下位互換性パッケージをインストールする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

WMI 下位互換性パッケージをインストールせずに、トポロジビルダーのマージウィザードを実行しようとすると、次のエラーが表示されます。

![WMI エラーメッセージ](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI エラーメッセージ")

WMI の下位互換性パッケージをインストールせずに**CsLegacytopology**コマンドレットを実行しようとすると、次のエラーが表示されます。

![Windows PowerShell WMI プロバイダーエラー](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI プロバイダーエラー")

WMI 下位互換性パッケージをインストールするには

1.  \\インストールメディアから、setup\\AMD64\\setup\\ocswmibc に移動します。MSI.

2.  OCSWMIBC をインストールします。MSI.
    
    <div>
    

    > [!IMPORTANT]  
    > [トポロジビルダー] マージウィザードが実行されているコンピューターに OCSWMIBC がインストールされている必要があります。 ただし、トポロジのすべてのフロントエンドサーバーに OCSWMIBC をインストールすることをお勧めします。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC は、Lync Server 2013 コアコンポーネントと Lync Server 2013 Management Shell がインストールされていて、Office Communications Server 2007 R2 のトポロジ (WMI プロバイダーから Active Directory ドメインにアクセスできる場合) に、ドメイン内のすべてのコンピューターにインストールできます。サービス (AD DS) と SQL Server)。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

