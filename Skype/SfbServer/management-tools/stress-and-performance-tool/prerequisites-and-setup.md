---
title: Busines Stress and Performance Tool Skypeの前提条件とセットアップ
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: 2015 年 2015 年Skype for Business Serverパフォーマンス ツールの要件または前提条件。 ストレスとパフォーマンス ツールをインストールまたはセットアップする方法。
ms.openlocfilehash: 87c42d63e394c6beea68c23b8e1d7cff7b07266c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771923"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Busines Stress and Performance Tool Skypeの前提条件とセットアップ
 
2015 年 2015 年Skype for Business Serverパフォーマンス ツールの要件または前提条件。 ストレスとパフォーマンス ツールをインストールまたはセットアップする方法。
  
ストレスとパフォーマンス ツールを実行する前に注意する必要があるハードウェア、ソフトウェア、およびシステム構成の要件については、次のセクションがあります。
  
- [クライアント のハードウェア要件](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [クライアント ソフトウェアの要件](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [構成要件](prerequisites-and-setup.md#ConfigReqs)
    
さらに[、2015](prerequisites-and-setup.md#Installing)年のストレスとパフォーマンス ツールのインストールに関するSkype for Business Serverセクションも用意されています。
  
## <a name="client-hardware-requirements"></a>クライアント のハードウェア要件
<a name="ClientHardwareReqs"> </a>

Skype for Business Server 2015 の展開に対してストレスとパフォーマンス ツールを実行する場合は、少なくとも、テストで 4500 人のユーザーごとに次のハードウェア要件を満たす必要があります。
  
- 1 ギガビット ネットワーク アダプター
    
- 8 GB RAM
    
- デュアルコア CPU 2 台
    
## <a name="client-software-requirements"></a>クライアント ソフトウェアの要件
<a name="ClientSoftwareReqs"> </a>

ストレスとパフォーマンス ツールでサポートされているオペレーティング システムは次のとおりです。
  
- Windows Server 2012
    
- WindowsServer 2008 (64 ビット)
    
さらに、コンピューターは次のソフトウェア要件を満たす必要があります。
  
- Microsoft .NET 4.5 Framework がインストールされている必要があります。 [.Net 4.5 Framework をダウンロードします。](https://www.microsoft.com/download/details.aspx?id=30653)
    
- デスクトップ エクスペリエンス機能は、デスクトップ エクスペリエンスで有効になっている必要Windows。
    
- 2013 Microsoft Visual C++ (x64) がインストールされている必要があります。 [ダウンロード Visual C++ 2013 here](https://www.microsoft.com/download/details.aspx?id=40784)
    
- 2015 年にSkype for Business Serverが必要です。
    
## <a name="configuration-requirements"></a>構成要件
<a name="ConfigReqs"> </a>

ストレスとパフォーマンス ツールを正常に実行するには、次の追加構成が必要です。
  
- ドメインまたはローカル管理者のグループのメンバーとしてサーバーにログインする必要があります。
    
- Skype for Business Server 2015 ユーザー作成ツール (UserProvisioningTool.exe) は、ユーザー アカウントが存在するフロント エンド サーバーまたは Standard Edition サーバーにはインストールできません。
    
- ユーザー作成ツールを複数回実行する場合は、Microsoft Unified Communications を有効にしている各ユーザーに一意の電話番号が必要です。
    
- ページ ファイルのサイズはシステムで管理する必要があります。それ以外の場合は、コンピューター システム内の RAM の量の 1.5 倍以上である必要があります。
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>2015 年Skype for Business Serverパフォーマンス ツールのインストール
<a name="Installing"> </a>

インストールを簡単に行う必要があります。 Windows インストーラー ファイル **CapacityPlanningTool.msi** を、ユーザー トラフィックのシミュレートに使用する各クライアント コンピューター上、およびユーザーと連絡先を作成する各プールのフロント エンド サーバーで実行する必要があります。
  
他の.msiに記載されているサンプル スクリプトと共に、Skype for Business Server [2015、Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367)をダウンロードするには、[ダウンロード センター] リンクに移動します。
  

