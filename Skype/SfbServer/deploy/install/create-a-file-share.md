---
title: Skype のビジネス サーバーのファイル共有を作成します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: '概要: は、Skype のビジネス サーバーのインストールの一部として、Windows サーバーのファイル共有を作成する方法を説明します。 ビジネスのサーバーで Microsoft の評価の中心からの Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: a6a040c60d3c5a41df8dfa24abd5948d85180f2e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884622"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Skype のビジネス サーバーのファイル共有を作成します。
 
**の概要:** Skype のビジネス サーバーのインストールの一部として、Windows サーバーのファイル共有を作成する方法について説明します。 ビジネスのサーバーで Microsoft の評価の中心からの Skype の無料試用版をダウンロード:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
ビジネス サーバーの Skype では、トポロジ内のコンピューターにファイルを交換できるように、ファイル共有が必要です。 Skype ビジネス サーバーのインストール プロセスでの 8 のステップ 2 は、ファイル共有を作成します。 手順 1 ～ 5 は任意の順序で実行できます。 ただし、図に示すように手順 6、7、および 8 では、手順 1 5 からの後を行う必要があります。 ファイル共有についての詳細を計画するため、 [Skype のビジネス サーバーの環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)や[ビジネス サーバー 2019 の Skype のサーバーの要件](../../../SfBServer2019/plan/system-requirements.md)を参照してください。
  
![概要図](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>基本的なファイル共有を作成する

ここでは、基本的な Windows Server ファイル共有を作成する方法を詳しく説明します。 ビジネス サーバーの Skype で基本的な Windows Server のファイル共有がサポートされています。 ただし、明示的には行いません高可用性を実現します。 高可用性環境が必要な場合は、分散ファイル システム (DFS) ファイル共有をお勧めします。 高可用性のファイル共有および DFS の詳細については、[高可用性とビジネスのサーバー用の Skype での災害復旧の計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)を参照してください。
  
> [!NOTE]
> Windows Server 2012 R2 は、Windows Server プラットフォームを使用した記憶域ネットワーク (SAN) のようなファイル共有ソリューションの提供において大きな飛躍を遂げました。 Windows Server 2012 R2 ストレージ ソリューションは従来の SAN ベースのアプライアンスに比べて、パフォーマンスへの影響を最小限に抑えつつコストを半減できます。 Windows Server 2012 R2 のファイル共有オプションの詳細については、 [Windows Server 2012 R2 のストレージ](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)ダウンロード可能なホワイト ペーパーを参照してください。 
  
**ファイル共有の作成**手順に関するビデオをご覧ください。
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>基本的なファイル共有を作成する

1. ファイル共有をホストするコンピューターにログオンします。
    
2. 共有するフォルダーを右クリックし、[**プロパティ**] を選択します。
    
3. [**共有**] タブを選択し、[**詳細な共有**] をクリックします。
    
4. [**このフォルダーを共有する**] をクリックします。
    
5. [**アクセス許可**] をクリックします。
    
6. ファイル共有をホストするサーバーのローカルの **Administrators** グループを追加し、**フル コントロール、変更、読み取り**の権限を付与し、[**OK**] をクリックします。
    
7. [**OK**] をもう一度クリックして、ネットワーク パスをメモします。
    
8. [**完了**] をクリックして、ウィザードを終了します。
    
     ![フォルダー共有のための [共有] タブ](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

