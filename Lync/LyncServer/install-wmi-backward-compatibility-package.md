---
title: WMI 下位互換パッケージをインストールする
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
ms.openlocfilehash: c59e3ea03b3b6f4085f8acf461b1da3f32e21fa9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>WMI 下位互換パッケージをインストールする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

WMI 下位互換パッケージをインストールせずにトポロジ ビルダー マージ ウィザードを実行しようとすると、次のエラーが表示されます。

![WMI エラーメッセージ](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI エラーメッセージ")

WMI 下位互換パッケージをインストールせずに **Merge-CsLegacytopology** コマンドレットを実行しようとすると、次のエラーが表示されます。

![Windows PowerShell WMI プロバイダーエラー](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI プロバイダーエラー")

WMI 下位互換パッケージをインストールするには

1.  インストールメディアから\\、[セットアップ\\AMD64\\セットアップ\\ocswmibc] に移動します。MSI.

2.  OCSWMIBC.MSI をインストールします。
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC.msi は、トポロジ ビルダー マージ ウィザードが実行されているコンピューターにインストールする必要があります。ただし、トポロジ内のすべてのフロントエンド サーバーに OCSWMIBC.msi をインストールすることをお勧めします。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC は、Lync Server 2013 コアコンポーネントと Lync Server 2013 管理シェルがインストールされているドメイン内の任意のコンピューターにインストールすることができ、Office Communications Server 2007 R2 トポロジ (WMI プロバイダーから Active Directory ドメインへのアクセス権) を持ちます。サービス (AD DS) および SQL Server)。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

