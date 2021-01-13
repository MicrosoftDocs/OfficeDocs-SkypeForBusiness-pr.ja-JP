---
title: Skype for Busines Stress and Performance Tool の前提条件とセットアップ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server 2015 Stress and Performance Tool の要件または前提条件。 Stress and Performance Tool をインストールまたはセットアップする方法。
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814957"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Skype for Busines Stress and Performance Tool の前提条件とセットアップ
 
Skype for Business Server 2015 Stress and Performance Tool の要件または前提条件。 Stress and Performance Tool をインストールまたはセットアップする方法。
  
Stress and Performance Tool を実行する前に知る必要があるハードウェア、ソフトウェア、およびシステム構成の要件については、次のセクションを参照してください。
  
- [クライアントのハードウェア要件](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [クライアント ソフトウェアの要件](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [構成要件](prerequisites-and-setup.md#ConfigReqs)
    
さらに[、Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)をインストールするセクションも以下に示します。
  
## <a name="client-hardware-requirements"></a>クライアント のハードウェア要件
<a name="ClientHardwareReqs"> </a>

Skype for Business Server 2015 展開に対して Stress and Performance Tool を実行する場合、少なくとも、テストで 4500 ユーザーごとにこれらのハードウェア要件を満たす必要があります。
  
- 1 ギガビット ネットワーク アダプター
    
- 8 GB RAM
    
- デュアルコア CPU 2 台
    
## <a name="client-software-requirements"></a>クライアント ソフトウェアの要件
<a name="ClientSoftwareReqs"> </a>

Stress and Performance Tool でサポートされているオペレーティング システムは次のとおりです。
  
- Windows Server 2012
    
- Windows Server 2008 (64 ビット)
    
さらに、コンピューターは次のソフトウェア要件を満たす必要があります。
  
- Microsoft .NET 4.5 Framework がインストールされている必要があります。 [ここに .Net 4.5 Framework をダウンロードしてください。](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Windows でデスクトップ エクスペリエンス機能を有効にする必要があります。
    
- Microsoft Visual C++ 2013 (x64) がインストールされている必要があります。 [Visual C++ 2013 をここからダウンロードする](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Skype for Business Server 2015 が正常に展開されている必要があります。
    
## <a name="configuration-requirements"></a>構成要件
<a name="ConfigReqs"> </a>

Stress and Performance Tool を正常に実行するには、次の追加構成が必要です。
  
- ドメインまたはローカル管理者のグループのメンバーとしてサーバーにログインする必要があります。
    
- Skype for Business Server 2015 ユーザー作成ツール (UserProvisioningTool.exe) は、ユーザー アカウントが存在するフロントエンド サーバーまたは Standard Edition サーバーにはインストールできません。
    
- ユーザー作成ツールを複数回実行する場合は、Microsoft Unified Communications が有効になっている各ユーザーに一意の電話番号が必要です。
    
- ページ ファイルのサイズはシステムで管理する必要があります。それ以外の場合は、コンピューター システムの RAM の容量の 1.5 倍以上である必要があります。
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool のインストール
<a name="Installing"> </a>

インストールを簡単に行う必要が生じなかった。 Windows インストーラー ファイル **CapacityPlanningTool.msi** を、ユーザー トラフィックのシミュレートに使用する各クライアント コンピューターで実行し、ユーザーと連絡先を作成する各プールのフロント エンド サーバーで実行する必要があります。
  
.msi を、他の記事で説明されているサンプル スクリプトと共にダウンロードするには、ダウンロード センターのリンク [(Skype for Business Server 2015、Stress and Performance Tool)](https://www.microsoft.com/download/details.aspx?id=50367)に移動します。
  

