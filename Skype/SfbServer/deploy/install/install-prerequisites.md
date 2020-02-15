---
title: Skype for Business Server の必須コンポーネントをインストールする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '概要: Skype for Business Server をインストールする前に構成する必要があるサーバーとサーバーの役割について説明します。 次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターから、無料の Skype For business Server の試用版をダウンロードしてください。'
ms.openlocfilehash: fedcebe601d21f0e581795c264ed26c6e90716bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018258"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Skype for Business Server の必須コンポーネントをインストールする
 
**概要:** Skype for Business Server をインストールする前に構成する必要があるサーバーとサーバーの役割について説明します。 [Microsoft 評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)から、無料の Skype For business Server の試用版をダウンロードします。
  
前提条件のインストールは、トポロジ内の各サーバーに必要な役割と機能をインストールすることによって、Windows Server をセットアップすることで構成されます。 要件は、サーバーがトポロジで満たす役割に基づいています。 手順1から5までを任意の順序で実行できます。 ただし、手順6、7、および8は、図に示されているように、手順 1 ~ 5 の後で実行する必要があります。 必須コンポーネントのインストール手順は 1 ~ 8 です。
  
![概要図-必須コンポーネントをインストールします。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Windows Server のセットアップ

Skype for Business Server をインストールするには、Windows Server オペレーティングシステムといくつかの前提条件が必要です。 前提条件の計画の詳細については、「 [Skype For Business server のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。 
  
> [!TIP]
> この手順では、Windows Server 2012 R2 を使用します。 異なるバージョンの Windows Server を使用している場合は、手順が若干異なることがあります。 
  
> [!IMPORTANT]
> 作業を開始する前に、windows Update を使用して Windows Server が最新の状態になっていることを確認してください。 
  
![Windows Server を最新の状態にします。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
**必須コンポーネントをインストール**するためのビデオの手順をご覧ください。
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>フロントエンドサーバーに必要な役割と機能をインストールする

サーバーマネージャーを使用して、必要な役割と機能をインストールすることができます。 
    
1. 「 [Skype For Business server のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」に記載されている前提条件のソフトウェア機能をインストールします。 必要なソフトウェアは、Skype for Business Server を実行するサーバー上に存在する必要があります。
    
    > [!CAUTION]
    > Windows Server 2012 R2 では、既定で必要な機能のソースファイルの一部がインストールされません。 サーバーがインターネットに接続されていない場合は、Windows Server 2012 R2 メディアを挿入して、必要な機能をインストールするために**別のソースパスを指定**する必要があります。 ソースファイルは sources\sxs ディレクトリにあります。 たとえば、Windows Server 2012 R2 メディアがドライブ D にある場合は、パスをに`d:\sources\sxs`設定します。 Windows Update から最新の更新プログラムを入手することが重要です。 インターネットに接続していない場合は、必要な更新プログラムに関連するすべての更新プログラムおよび必須コンポーネントを手動でインストールする必要があります。 
  
1. インストールが完了したことを示すダイアログボックスが表示されたら、サーバーを再起動して処理を完了する必要があります。
    
1. **Windows Update**を再度実行して、インストールされた役割とサービスに対する更新があるかどうかを確認します。
    
1. このサーバーで Skype for Business Server コントロールパネルを使用する場合は、Silverlight もインストールする必要があります。 Silverlight をインストールするには、「 [Microsoft silverlight](https://www.microsoft.com/silverlight/)」を参照してください。


> [!IMPORTANT]
> ディレクター、常設チャット、エッジの役割など、フロントエンドサーバー以外の役割を実行しているサーバーの前提条件には、独自の前提条件があります。 各サーバーの種類で必要とされる正確な前提条件の詳細については、「 [Skype For Business server のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。 
  

