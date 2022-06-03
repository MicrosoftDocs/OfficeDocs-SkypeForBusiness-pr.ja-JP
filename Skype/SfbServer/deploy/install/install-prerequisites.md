---
title: Skype for Business Serverの前提条件をインストールする
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: '概要: Skype for Business Serverをインストールする前に構成する必要があるサーバーとサーバーの役割について説明します。'
ms.openlocfilehash: d946b694ea527236b8ce6f4b7b562df9fa025011
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860738"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Skype for Business Serverの前提条件をインストールする
 
**概要：** Skype for Business Serverをインストールする前に構成する必要があるサーバーとサーバーの役割について説明します。
  
前提条件のインストールは、トポロジ内の各サーバーに必要なロールと機能をインストールして、Windows サーバーを設定することで構成されます。 要件は、サーバーがトポロジで満たすロールに基づいています。 手順 1 ~ 5 は、任意の順序で実行できます。 ただし、図に示すように、手順 6、7、および 8 を順番に実行し、手順 1 ~ 5 の後に実行する必要があります。 前提条件のインストールは、手順 1/ 8 です。
  
![概要図 - 前提条件をインストールします。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Windows サーバーのセットアップ

Skype for Business Serverインストールするには、Windows サーバー オペレーティング システムと多くの前提条件が必要です。 前提条件の計画の詳細については、「[Skype for Business Serverのサーバー要件」を](../../../SfBServer2019/plan/system-requirements.md)参照してください。 
  
> [!TIP]
> この手順では、Windows Server 2012 R2 を使用します。 別のバージョンのWindows サーバーを使用している場合は、手順が若干異なる可能性があります。 
  
> [!IMPORTANT]
> 開始する前に、Windows Updateを使用して、Windows Server が最新であることを確認します。 
  
![Windows サーバーを最新の状態にします。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
インストールの前提条件については、ビデオの手順 **をご覧ください。**
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>フロントエンド サーバーに必要なロールと機能をインストールする

サーバー マネージャーを使用して、必要なロールと機能をインストールできます。 
    
1. [Skype for Business Serverのサーバー要件](../../../SfBServer2019/plan/system-requirements.md)に記載されている前提条件のソフトウェア機能をインストールします。 必要なソフトウェアは、Skype for Business Serverを実行するサーバー上にある必要があります。
    
    > [!CAUTION]
    > Windows Server 2012 R2 では、既定で必要な機能のすべてのソース ファイルがインストールされるわけではありません。 サーバーがインターネットに接続されていない場合は、Windows Server 2012 R2 メディアを挿入し、[**代替ソース パスの指定**] を選択して必要な機能をインストールする必要があります。 ソース ファイルは source\sxs ディレクトリにあります。 たとえば、Windows Server 2012 R2 メディアがドライブ D にある場合は、パス`d:\sources\sxs`を . Windows Updateからの最新の更新プログラムを用意しておくことが重要です。 インターネットに接続していない場合は、関連するすべての更新プログラムと、必要な更新プログラムの前提条件を手動でインストールする必要があります。 
  
1. ダイアログ ボックスにインストールが完了したことが示されたら、サーバーを再起動してプロセスを完了する必要があります。
    
1. **Windows Update** もう一度実行して、インストールされたロールとサービスに更新プログラムがあるかどうかを確認します。
    
1. このサーバーでSkype for Business Server コントロール パネルを使用する場合は、Silverlight もインストールする必要があります。 Silverlight をインストールするには、 [Microsoft Silverlight に関するページを](https://www.microsoft.com/silverlight/)参照してください。


> [!IMPORTANT]
> ディレクター、常設チャット、Edge の役割など、フロントエンド サーバー以外の役割を実行するサーバーの前提条件には、独自の前提条件があります。 各サーバーの種類に必要な正確な前提条件の詳細については、「[Skype for Business Serverのサーバー要件」を](../../../SfBServer2019/plan/system-requirements.md)参照してください。 
  

