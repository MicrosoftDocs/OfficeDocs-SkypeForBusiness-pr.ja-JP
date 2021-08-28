---
title: サーバーの前提条件をインストールSkype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '概要: サーバーをインストールする前に構成する必要があるサーバーとサーバーの役割Skype for Business Server。 以下の Microsoft 評価センター Skype for Business Server無料試用版をダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 998fa2371e0d0b0d62ce3755a6be881f49956eef
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624369"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>サーバーの前提条件をインストールSkype for Business Server
 
**概要:** サーバーをインストールする前に構成する必要があるサーバーとサーバーの役割Skype for Business Server。 Microsoft 評価センターからSkype for Business Server試用版[をダウンロードします](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
前提条件のインストールは、トポロジ内Windows各サーバーに必要な役割と機能をインストールして、サーバーをセットアップすることで構成されます。 要件は、サーバーがトポロジで果たす役割に基づいて行います。 手順 1 ~ 5 は、任意の順序で実行できます。 ただし、図に示されている手順 6、7、および 8 を順番に実行し、手順 1 ~ 5 の後に実行する必要があります。 前提条件のインストールは、手順 1 ~ 8 です。
  
![概要図 - 前提条件をインストールします。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>セットアップ Windows サーバー

Skype for Business Serverするには、Windowsサーバー オペレーティング システムと多くの前提条件が必要です。 前提条件の計画の詳細については、「[サーバー要件」を参照Skype for Business Server。](../../../SfBServer2019/plan/system-requirements.md) 
  
> [!TIP]
> この手順では、R2 Windows Server 2012使用します。 別のバージョンのサーバーを使用している場合Windows手順が若干異なる場合があります。 
  
> [!IMPORTANT]
> 開始する前に、Windows Update を使用して、サーバーが最新Windowsしてください。 
  
![Windowsサーバーを最新の情報に更新します。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
インストールの前提条件については、ビデオ **の手順をご覧ください**。
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>フロントエンド サーバーに必要な役割と機能をインストールする

サーバー マネージャーを使用して、必要な役割と機能をインストールできます。 
    
1. 「サーバー要件」に記載されている必須ソフトウェア機能をインストール[Skype for Business Server。](../../../SfBServer2019/plan/system-requirements.md) 必要なソフトウェアは、そのソフトウェアを実行するサーバー上Skype for Business Server。
    
    > [!CAUTION]
    > Windows Server 2012R2 は、既定では、必要な機能のすべてのソース ファイルをインストールする必要はありません。 サーバーがインターネットに接続されていない場合は、Windows Server 2012 R2 メディアを挿入し、[別のソース パスを指定する] を選択して、必要な機能をインストールする必要があります。 ソース ファイルは sources\sxs ディレクトリにあります。 たとえば、R2 メディアWindows Server 2012ドライブ D にある場合は、パスをに設定します `d:\sources\sxs` 。 更新プログラムから最新の更新プログラムを取得することがWindowsです。 インターネットに接続していない場合は、関連するすべての更新プログラムと、必要な更新プログラムの前提条件を手動でインストールする必要があります。 
  
1. インストールが完了したというダイアログ ボックスが表示された場合は、サーバーを再起動してプロセスを完了する必要があります。
    
1. **[Windows更新]** を再度実行して、インストールされた役割とサービスに対する更新プログラムが含まれています。
    
1. このサーバーでコントロール パネルSkype for Business Serverする場合は、Silverlight もインストールする必要があります。 Silverlight をインストールするには [、「Microsoft Silverlight」を参照してください](https://www.microsoft.com/silverlight/)。


> [!IMPORTANT]
> ディレクター、常設チャット、エッジの役割など、フロントエンド サーバー以外の役割を実行するサーバーの前提条件には、独自の前提条件があります。 各サーバーの種類に必要な正確な前提条件の詳細については、「サーバー要件」を参照[Skype for Business Server。](../../../SfBServer2019/plan/system-requirements.md) 
  

