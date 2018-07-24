---
title: Skype for Busines Stress and Performance Tool の前提条件と設定
ms.author: heidip
author: microsoftheidi
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Skype for Business Server 2015 Stress and Performance Tool の前提条件と設定。 Stress and Performance Tool のインストールまたは設定方法。
ms.openlocfilehash: fbc04202ea9b0719be9b8221d43171d58fe772b7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20995292"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Skype for Busines Stress and Performance Tool の前提条件と設定
 
Skype for Business Server 2015 Stress and Performance Tool の前提条件と設定。 Stress and Performance Tool のインストールまたは設定方法。
  
Stress and Performance Tool を実行する前に注意する必要のあるハードウェア、ソフトウェア、システム構成の要件について、次のセクションに示します。
  
- [クライアントのハードウェア要件](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [クライアントのソフトウェア要件](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [構成要件](prerequisites-and-setup.md#ConfigReqs)
    
さらに、後述のセクションで [Skype for Business Server 2015 Stress and Performance Tool のインストール](prerequisites-and-setup.md#Installing)についても説明します。
  
## <a name="client-hardware-requirements"></a>クライアントのハードウェア要件
<a name="ClientHardwareReqs"> </a>

Skype for Business Server 2015 の展開で Stress and Performance Tool を実行する場合、少なくとも、テスト内の 4500 人のユーザーに対して次のハードウェア要件を満たす必要があります。
  
- 1 ギガビットのネットワーク アダプター
    
- 8 GB RAM
    
- 2 基のデュアルコア CPU
    
## <a name="client-software-requirements"></a>クライアントのソフトウェア要件
<a name="ClientSoftwareReqs"> </a>

Stress and Performance Tool のサポートされるオペレーティング システムは次のとおりです。
  
- Windows Server 2012
    
- Windows Server 2008 (64 ビット)
    
これに加え、コンピューターは次のソフトウェア要件を満たす必要があります。
  
- Microsoft .NET 4.5 Framework がインストールされている必要があります。 [.Net 4.5 のダウンロードここでのフレームワークです。](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- Windows でデスクトップ エクスペリエンス機能を有効にする必要があります。
    
- Microsoft Visual C++ 2013 (x64) がインストールされている必要があります。 [Visual C++ 2013 をここからダウンロードします。](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- 正常に展開された Skype for Business Server 2015 が必要になります。
    
## <a name="configuration-requirements"></a>構成要件
<a name="ConfigReqs"> </a>

Stress and Performance Tool を正常に実行するには、次に示す追加の構成が必要となります。
  
- ドメインまたはローカル管理者グループのメンバーとしてサーバーにログインする必要があります。
    
- ユーザー アカウントが存在するいかなるフロント エンド サーバーまたは Standard Edition サーバーにも Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) をインストールすることはできません。
    
- User Creation Tool が複数回実行される場合、Microsoft Unified Communications を使用できるユーザーは各自ユニークな電話番号を所有する必要があります。
    
- ページのファイル サイズはシステムにより管理されるか、最小でもコンピューター システム内の RAM の容量の 1.5 倍である必要があります。
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool のインストール
<a name="Installing"> </a>

インストールはとても簡単です。 Windows のインストーラー ファイル、**CapacityPlanningTool.msi** を、ユーザー トラフィックのシミュレートのために使用する各クライアント コンピューターで、およびユーザーと連絡先を作成する各プール内のフロントエンド サーバーで実行する必要があります。
  
ダウンロード センターのリンクには、他の記事に記載されているサンプル スクリプトと、.msi をダウンロードする: [Skype ビジネス サーバー 2015、ストレスおよびパフォーマンス ツール](https://www.microsoft.com/download/details.aspx?id=50367)です。
  

