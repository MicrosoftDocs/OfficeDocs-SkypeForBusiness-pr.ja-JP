---
title: Skype for Business Server でファイル共有を作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: '概要: Skype for Business Server のインストールの一部として Windows Server ファイル共有を作成する方法について説明します。 Skype for Business Server の無料トライアルは、次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターからダウンロードしてください。'
ms.openlocfilehash: d6a34ad4807948a5580fc572628a4fd6333dd9f8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292166"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Skype for Business Server でファイル共有を作成する
 
**概要:** Skype for Business Server のインストールの一部として Windows Server ファイル共有を作成する方法について説明します。 Skype for Business Server の無料トライアルは、次[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)の Microsoft 評価センターからダウンロードしてください。
  
Skype for Business Server を使用するには、トポロジ内のコンピューターがファイルを交換できるようにファイル共有が必要です。 ファイル共有を作成するには、Skype for Business Server のインストールプロセスの手順2/3 を実行します。 手順 1 ～ 5 は任意の順序で実行できます。 ただし、手順6、7、8を順番に実行する必要があります。また、図に示されている手順 1 ~ 5 の後に行う必要があります。 ファイル共有の詳細については、「skype for business [server の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」または「 [Skype for business Server 2019 のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。
  
![概要図](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>基本的なファイル共有を作成する

ここでは、基本的な Windows Server ファイル共有を作成する方法を詳しく説明します。 Windows Server の基本的なファイル共有は、Skype for Business Server でサポートされています。 ただし、高可用性を明示的に提供するわけではありません。 高可用性環境が必要な場合は、分散ファイル システム (DFS) ファイル共有をお勧めします。 高可用性ファイルの共有と DFS の詳細については、「 [Skype For Business Server で高可用性と障害回復を計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)する」を参照してください。
  
> [!NOTE]
> Windows Server 2012 R2 は、Windows Server プラットフォームを使用した記憶域ネットワーク (SAN) のようなファイル共有ソリューションの提供において大きな飛躍を遂げました。 Windows Server 2012 R2 ストレージ ソリューションは従来の SAN ベースのアプライアンスに比べて、パフォーマンスへの影響を最小限に抑えつつコストを半減できます。 Windows Server 2012 R2 のファイル共有オプションの詳細については、ダウンロード可能なホワイトペーパー [Windows server 2012 R2 ストレージ](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)を参照してください。 
  
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
  
> [!NOTE]
>ファイルストアが DFS 共有でホストされている場合は、次の警告が表示されます。

警告: "\\<domain>\<share>" の共有アクセス許可にアクセスできません。

>これは、ファイルサーバーの管理者ではないか、または分散ファイルシステム (DFS) 共有である場合に発生します。 共有のアクセス許可が既に構成されている場合は、この警告を無視できます。 新しい共有の場合は、共有のアクセス許可を手動で構成する方法に関するドキュメントを参照してください。

>DFS 共有の共有アクセス許可にアクセスできないため、Skype for Business Server では、ファイル共有に対して明示的にグループを設定することはできません。 Skype for Business Server コンポーネントが適切な権限を持つファイル共有にアクセスできるようにするには、フルコントロールの共有アクセス許可を持つローカル管理者に加えて、次の RTC グループが追加されていることを確認します。

RTCHSUniversalServices RTCComponentUniversalServices RTCUniversalServerAdmins
