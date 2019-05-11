---
title: ビジネス サーバーの Skype のための前提条件をインストールします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '概要: については、サーバーとサーバーの役割の業務サーバーの Skype をインストールする前に構成する必要があります。 ビジネスのサーバーで Microsoft の評価の中心からの Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 6a5b6728f65d1f541687cb55811157531c70456d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891811"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>ビジネス サーバーの Skype のための前提条件をインストールします。
 
**の概要:** サーバーとサーバーのビジネスの Skype をインストールする前に構成する必要がありますサーバーの役割について説明します。 [マイクロソフト評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)からビジネス サーバー用には、Skype の無料試用版をダウンロードします。
  
必須コンポーネントのインストールは、トポロジ内のサーバーごとに必要な役割と機能をインストールすることによって Windows のサーバーを設定するので構成されます。 要件は、サーバーをトポロジに満たす役割に基づいています。 手順 1 ～ 5 は任意の順序で実行できます。 ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。 8 のステップ 1 は、必須コンポーネントをインストールします。
  
![概要図 - インストールの前提条件](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Windows Server をセットアップする

Skype ビジネス サーバー用には、インストールする前に Windows サーバー オペレーティング システムおよび前提条件の数値が必要があります。 前提条件の計画に関する詳細については、 [Skype ビジネス サーバー用のサーバーの要件](../../../SfBServer2019/plan/system-requirements.md)を参照してください。 
  
> [!TIP]
> この手順では Windows Server 2012 R2 を使用します。 別のバージョンの Windows Server を使用する場合は、手順が若干異なることがあります。 
  
> [!IMPORTANT]
> 作業を開始する前に、Windows Server は、Windows Update を使用して最新の状態を確認します。 
  
![Windows Server を最新の状態にする](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
**前提条件のインストール**手順に関するビデオを見てください。
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>フロントエンド サーバーに必要な役割と機能をインストールする

必要な役割と機能はサーバー マネージャーを使用してをインストールすることができます。 
    
1. [Skype ビジネス サーバー用のサーバーの要件](../../../SfBServer2019/plan/system-requirements.md)に記載されている前提条件のソフトウェア機能をインストールします。 Skype ビジネス サーバーを実行するサーバー上で必要なソフトウェアがある必要があります。
    
    > [!CAUTION]
    > 既定では、必要な機能のソース ファイルのすべてが Windows Server 2012 R2 でインストールされるわけではありません。 サーバーがインターネットに接続されていない場合は、必要な機能をインストールするために、Windows Server 2012 R2 メディアを挿入し、[**代替ソース パスの指定**] を選択する必要があります。 ソース ファイルは sources\sxs ディレクトリにあります。 たとえば、Windows Server 2012 R2 のメディアがドライブ D の場合は、設定のパス`d:\sources\sxs`。 Windows Update で最新の更新プログラムを入手しておいてください。 インターネットに接続していない場合は、関連するすべての更新プログラムと、必要な更新プログラムの前提条件を手動でインストールする必要があります。 
  
1. ダイアログ ボックスにインストールの完了が通知されたら、サーバーを再起動して処理を完了させる必要があります。
    
1. インストールした役割とサービスの更新プログラムがないかどうかを確認するために、**Windows Update** を再度実行します。
    
1. 使用する Skype ビジネス サーバーのコントロール パネルのこのサーバーの場合、Silverlight もインストールする必要があります。 Silverlight をインストールするには、 [Microsoft Silverlight](https://www.microsoft.com/silverlight/)を参照してください。


> [!IMPORTANT]
> ディレクター、常設チャット、エッジなど、フロントエンド サーバー以外の役割を実行するサーバーには、また別の前提条件があります。 サーバーの種類ごとに必要な正確な前提条件の詳細については、 [Skype ビジネス サーバー用のサーバーの要件](../../../SfBServer2019/plan/system-requirements.md)を参照してください。 
  

