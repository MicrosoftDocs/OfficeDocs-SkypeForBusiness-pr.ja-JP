---
title: Skype for Business Server の前提条件をインストールする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '概要: Skype for Business Server をインストールする前に構成する必要があるサーバーとサーバーの役割について説明します。 Skype for Business Server の無料トライアルは、次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターからダウンロードしてください。'
ms.openlocfilehash: 2fbf90a1ee6f517cad2c716e6a50dd814352993e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240607"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Skype for Business Server の前提条件をインストールする
 
**概要:** Skype for Business Server をインストールする前に構成する必要があるサーバーとサーバーの役割について説明します。 [Microsoft の評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)から Skype For business Server の無料トライアルをダウンロードします。
  
前提条件のインストールは、トポロジの各サーバーに必要な役割と機能をインストールして、Windows Server をセットアップすることで構成されています。 要件は、トポロジでサーバーが満たす役割に基づいています。 手順 1 ～ 5 は任意の順序で実行できます。 ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。 前提条件のインストールは、手順 1/8 です。
  
![概要図 - インストールの前提条件](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Windows Server をセットアップする

Skype for Business Server をインストールするには、Windows Server オペレーティングシステムといくつかの前提条件が必要です。 前提条件の計画の詳細については、「 [Skype For Business server のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。 
  
> [!TIP]
> この手順では Windows Server 2012 R2 を使用します。 別のバージョンの Windows Server を使用する場合は、手順が若干異なることがあります。 
  
> [!IMPORTANT]
> 作業を始める前に、windows Server が Windows Update を使用して最新の状態になっていることを確認します。 
  
![Windows Server を最新の状態にする](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
**前提条件のインストール**手順に関するビデオを見てください。
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>フロントエンド サーバーに必要な役割と機能をインストールする

サーバーマネージャーを使用して、必要な役割と機能をインストールできます。 
    
1. 「 [Skype For Business server のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」に記載されている必須ソフトウェア機能をインストールします。 必要なソフトウェアは、Skype for Business Server を実行するサーバー上にある必要があります。
    
    > [!CAUTION]
    > 既定では、必要な機能のソース ファイルのすべてが Windows Server 2012 R2 でインストールされるわけではありません。 サーバーがインターネットに接続されていない場合は、必要な機能をインストールするために、Windows Server 2012 R2 メディアを挿入し、[**代替ソース パスの指定**] を選択する必要があります。 ソース ファイルは sources\sxs ディレクトリにあります。 たとえば、Windows Server 2012 R2 メディアがドライブ D にある場合は、パスをに`d:\sources\sxs`設定します。 Windows Update で最新の更新プログラムを入手しておいてください。 インターネットに接続していない場合は、関連するすべての更新プログラムと、必要な更新プログラムの前提条件を手動でインストールする必要があります。 
  
1. ダイアログ ボックスにインストールの完了が通知されたら、サーバーを再起動して処理を完了させる必要があります。
    
1. インストールした役割とサービスの更新プログラムがないかどうかを確認するために、**Windows Update** を再度実行します。
    
1. このサーバーで Skype for Business Server コントロールパネルを使用する場合は、Silverlight をインストールする必要もあります。 Silverlight をインストールするには、「 [Microsoft silverlight](https://www.microsoft.com/silverlight/)」を参照してください。


> [!IMPORTANT]
> ディレクター、常設チャット、エッジなど、フロントエンド サーバー以外の役割を実行するサーバーには、また別の前提条件があります。 各サーバーの種類に必要な前提条件の詳細については、「 [Skype For Business server のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。 
  

