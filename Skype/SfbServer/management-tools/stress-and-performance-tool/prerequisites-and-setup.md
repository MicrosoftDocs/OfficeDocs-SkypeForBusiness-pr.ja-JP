---
title: Skype for Busines ストレスおよびパフォーマンスツールの前提条件とセットアップ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Skype for Business Server 2015 ストレスおよびパフォーマンスツールの要件または前提条件。 ストレスとパフォーマンスツールをインストールまたはセットアップする方法について説明します。
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005982"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Skype for Busines ストレスおよびパフォーマンスツールの前提条件とセットアップ
 
Skype for Business Server 2015 ストレスおよびパフォーマンスツールの要件または前提条件。 ストレスとパフォーマンスツールをインストールまたはセットアップする方法について説明します。
  
次のセクションでは、ストレスおよびパフォーマンスツールを実行する前に知っておく必要があるハードウェア、ソフトウェア、およびシステム構成の要件について説明しています。
  
- [クライアントハードウェアの要件](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [クライアントソフトウェアの要件](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [構成要件](prerequisites-and-setup.md#ConfigReqs)
    
また、 [Skype For Business Server 2015 ストレスおよびパフォーマンスツールをインストール](prerequisites-and-setup.md#Installing)するための以下のセクションもあります。
  
## <a name="client-hardware-requirements"></a>クライアントハードウェアの要件
<a name="ClientHardwareReqs"> </a>

Skype for Business Server 2015 展開に対してストレスおよびパフォーマンスツールを実行する場合は、少なくとも、テスト内のすべてのユーザー4500に対してこれらのハードウェア要件を満たす必要があります。
  
- 1ギガビットのネットワークアダプター
    
- 8 GB RAM
    
- 2つのデュアルコア Cpu
    
## <a name="client-software-requirements"></a>クライアントソフトウェアの要件
<a name="ClientSoftwareReqs"> </a>

ストレスおよびパフォーマンスツールでサポートされているオペレーティングシステムは次のとおりです。
  
- Windows Server 2012
    
- Windows Server 2008 (64 ビット)
    
また、コンピューターは次のソフトウェア要件を満たす必要があります。
  
- Microsoft .NET 4.5 Framework がインストールされている必要があります。 [.Net 4.5 Framework をダウンロードしてください。](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Windows では、デスクトップ環境の機能を有効にする必要があります。
    
- Microsoft Visual C++ 2013 (x64) がインストールされている必要があります。 [Visual C++ 2013 をダウンロードする](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Skype for Business Server 2015 が正常に展開されている必要があります。
    
## <a name="configuration-requirements"></a>構成要件
<a name="ConfigReqs"> </a>

ストレスとパフォーマンスツールを正常に実行するには、次の追加の構成が必要になります。
  
- ドメインまたはローカル管理者のグループのメンバーとしてサーバーにログインする必要があります。
    
- ユーザーアカウントが存在するフロントエンドサーバーまたは Standard Edition サーバーには、Skype for Business Server 2015 ユーザー作成ツール (Usermsiexec.exe Tool) をインストールすることはできません。
    
- ユーザー作成ツールを複数回実行する場合、Microsoft ユニファイドコミュニケーションが有効になっている各ユーザーは、一意の電話番号を持っている必要があります。
    
- ページファイルのサイズは、システムによって管理されている必要があります。それ以外の場合は、コンピューターシステムの RAM の容量の少なくとも1.5 倍にする必要があります。
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 ストレスおよびパフォーマンスツールのインストール
<a name="Installing"> </a>

インストールは簡単に行うことができませんでした。 ユーザートラフィックをシミュレートするために使用する各クライアントコンピューターで、またはユーザーと連絡先を作成する各プールのフロントエンドサーバーで、Windows インストーラファイル**CapacityPlanningTool**を実行する必要があります。
  
.Msi をダウンロードするには、その他の記事に記載されているサンプルスクリプトを使用して、「 [Skype For Business Server 2015、ストレスおよびパフォーマンスツール](https://www.microsoft.com/download/details.aspx?id=50367)」のダウンロードセンターへのリンクを参照してください。
  

