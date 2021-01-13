---
title: Skype for Business Server の前提条件のインストール
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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '概要: Skype for Business Server をインストールする前に構成する必要があるサーバーとサーバーの役割について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 197f2482bd6c53f3cf9814dbf6f36bb6c4bdb331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801717"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Skype for Business Server の前提条件のインストール
 
**概要:** Skype for Business Server をインストールする前に構成する必要があるサーバーとサーバーの役割について確認します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版 [をダウンロードします](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
前提条件のインストールは、トポロジ内の各サーバーに必要な役割と機能をインストールして、Windows Server をセットアップすることで構成されます。 要件は、サーバーがトポロジで果たす役割に基づいて行います。 手順 1. ~ 5. は任意の順序で実行できます。 ただし、手順 6、7、および 8 は、図に示されている順序、および手順 1 ~ 5 の後に実行する必要があります。 前提条件のインストールは、手順 1/8 です。
  
![概要図 - 前提条件をインストールします。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Windows Server のセットアップ

Skype for Business Server をインストールするには、Windows Server オペレーティング システムと多くの前提条件が必要です。 前提条件の計画の詳細については [、「Skype for Business Server のサーバー要件」を参照してください](../../../SfBServer2019/plan/system-requirements.md)。 
  
> [!TIP]
> この手順では、R2 Windows Server 2012使用します。 別のバージョンの Windows Server を使用している場合は、手順が若干異なる可能性があります。 
  
> [!IMPORTANT]
> 始める前に、Windows Update を使用して Windows Server が最新の情報に更新されている必要があります。 
  
![Windows Server を最新の情報に更新しました。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
インストールの前提条件については、ビデオ **の手順をご覧ください**。
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>フロントエンド サーバーに必要な役割と機能をインストールする

サーバー マネージャーを使用して、必要な役割と機能をインストールできます。 
    
1. Skype for Business Server のサーバー要件に記載 [されている必要なソフトウェア機能をインストールします](../../../SfBServer2019/plan/system-requirements.md)。 必要なソフトウェアは、Skype for Business Server を実行するサーバー上に必要です。
    
    > [!CAUTION]
    > Windows Server 2012 R2 では、既定で必要な機能のすべてのソース ファイルがインストールされるという動作ではありません。 サーバーがインターネットに接続されていない場合、必要な機能をインストールするには、Windows Server 2012 R2 メディアを挿入し、[代替ソース パスの指定] を選択する必要があります。 ソース ファイルは sources\sxs ディレクトリにあります。 たとえば、R2 メディアWindows Server 2012ドライブ D にある場合は、パスを次の値に設定します `d:\sources\sxs` 。 Windows Update から最新の更新プログラムを取得することが重要です。 インターネットに接続していない場合は、関連するすべての更新プログラムと、必要な更新プログラムの前提条件を手動でインストールする必要があります。 
  
1. インストールが完了したというダイアログ ボックスが表示された場合は、サーバーを再起動してプロセスを完了する必要があります。
    
1. **Windows Update を再度** 実行して、インストールされた役割とサービスに対する更新プログラムがインストールされていないか確認します。
    
1. このサーバーで Skype for Business Server コントロール パネルを使用する場合は、Silverlight もインストールする必要があります。 Silverlight をインストールするには [、Microsoft Silverlight を参照してください](https://www.microsoft.com/silverlight/)。


> [!IMPORTANT]
> ディレクター、常設チャット、エッジの役割など、フロントエンド サーバー以外の役割を実行するサーバーの前提条件には、独自の前提条件があります。 各サーバーの種類に必要な正確な前提条件の詳細については [、「Skype for Business Server のサーバー要件」を参照してください](../../../SfBServer2019/plan/system-requirements.md)。 
  

