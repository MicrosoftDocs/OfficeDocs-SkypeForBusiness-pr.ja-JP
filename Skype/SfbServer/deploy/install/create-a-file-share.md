---
title: Skype for Business Server でファイル共有を作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
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
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: '概要: Skype for Business Server のインストールの一環として Windows Server ファイル共有を作成する方法について説明します。 次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターから、無料の Skype For business Server の試用版をダウンロードしてください。'
ms.openlocfilehash: 74c2c8ddedfb6c2a751822fec51636dddd7747dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028298"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Skype for Business Server でファイル共有を作成する
 
**概要:** Skype for Business Server のインストールの一環として Windows Server ファイル共有を作成する方法について説明します。 次[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)の Microsoft 評価センターから、無料の Skype For business Server の試用版をダウンロードしてください。
  
Skype for Business Server では、トポロジ内のコンピューターがファイルを交換できるように、ファイル共有が必要になります。 Skype for Business Server のインストールプロセスでは、ファイル共有の作成は手順 2/8 です。 手順1から5までを任意の順序で実行できます。 ただし、手順6、7、および8は、図で説明されている手順 1 ~ 5 の後で実行する必要があります。 ファイル共有の詳細な計画については、「skype for business [server の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」または「 [Skype for Business server のサーバー要件 2019](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。
  
![概要図](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>基本的なファイル共有を作成する

このセクションでは、基本的な Windows Server ファイル共有を作成する手順について説明します。 Windows Server の基本的なファイル共有は、Skype for Business Server でサポートされています。 ただし、高可用性は明示的には提供されません。 高可用性環境では、分散ファイルシステム (DFS) ファイル共有をお勧めします。 高可用性ファイル共有と DFS の詳細については、「 [Plan for high availability and disaster recovery In Skype For Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。
  
> [!NOTE]
> Windows Server 2012 R2 では、Windows Server プラットフォームを使用してストレージエリアネットワーク (SAN) のようなファイル共有ソリューションを提供することによって、大きな飛躍が行われました。 従来の SAN ベースのアプライアンスと比較すると、Windows Server 2012 R2 ストレージソリューションは、パフォーマンスへの影響を最小限に抑えてコストを半分に削減することができます。 Windows Server 2012 R2 のファイル共有オプションの詳細については、ダウンロード可能なホワイトペーパー「 [Windows server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)」を参照してください。 
  
**ファイル共有を作成**するためのビデオの手順をご覧ください。
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>基本的なファイル共有を作成する

1. ファイル共有をホストするコンピューターにログオンします。
    
2. 共有を計画しているフォルダーを右クリックし、[**プロパティ**] を選択します。
    
3. [**共有**] タブを選択し、[**詳細な共有**] をクリックします。
    
4. [**このフォルダーを共有**する] をクリックします。
    
5. **[アクセス許可]** をクリックします。
    
6. ファイル共有をホストしているサーバーのローカル**管理者**グループを追加し、[**許可: フルコントロール]、[変更]、および [読み取り**] 権限を付与して、[ **OK**] をクリックします。
    
7. もう一度 [ **OK]** をクリックして、ネットワークパスを書き留めます。
    
8. [**完了**] をクリックしてウィザードを閉じます。
    
     ![フォルダーを共有するための [共有] タブ](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>ファイルストアが DFS 共有でホストされている場合、次の警告が表示されます。

警告: "\\<domain>\<share>" の共有アクセス許可にアクセスできません。

>これは、ファイルサーバーの管理者ではない場合や、これが分散ファイルシステム (DFS) 共有である場合に想定されます。 共有のアクセス許可が既に構成されている場合は、この警告を無視できます。 新しい共有の場合は、共有のアクセス許可を手動で構成する方法の詳細については、ドキュメントを参照してください。

>DFS 共有の共有アクセス許可にアクセスできないため、Skype for Business Server ではファイル共有のグループを明示的に設定することはできません。 Skype for Business Server コンポーネントが適切なアクセス許可を使用してファイル共有にアクセスできるようにするには、フルコントロール共有のローカル管理者に加えて、読み取りおよび変更レベルの共有アクセス許可を使用して、次の RTC グループが追加されるようにします。設定.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
