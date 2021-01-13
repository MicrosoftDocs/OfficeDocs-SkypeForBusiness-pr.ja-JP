---
title: Skype for Business Server でファイル共有を作成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: Skype for Business Server のインストールの一部として Windows Server ファイル共有を作成する方法について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 63ed4c54154698336bea7adb87db4e81d5fd35b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812237"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Skype for Business Server でファイル共有を作成する
 
**概要:** Skype for Business Server のインストールの一部として Windows Server ファイル共有を作成する方法について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。
  
Skype for Business Server では、トポロジ全体のコンピューターがファイルを交換できるよう、ファイル共有が必要です。 ファイル共有の作成は、Skype for Business Server のインストール プロセスの手順 2/8 です。 手順 1. ~ 5. は任意の順序で実行できます。 ただし、手順 6、7、および 8 を順番に実行し、図に示されている手順 1 ~ 5 の後に実行する必要があります。 ファイル共有の計画の詳細については [、「Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server [requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。
  
![概要図](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>基本的なファイル共有を作成する

このセクションでは、基本的な Windows Server ファイル共有を作成する方法について説明します。 基本的な Windows Server ファイル共有は、Skype for Business Server でサポートされています。 ただし、明示的に高可用性を提供するわけではありません。 高可用性環境では、分散ファイル システム (DFS) ファイル共有をお勧めします。 高可用性ファイル共有と DFS の詳細については [、「Plan for high availability and disaster recovery in Skype for Business Server 」を参照してください](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
> [!NOTE]
> Windows Server 2012 R2 は、Windows Server プラットフォームを使用して記憶域ネットワーク (SAN) に似たファイル共有ソリューションを提供する上で大きな飛び上がりを見た。 従来の SAN ベースのアプライアンスと比較すると、Windows Server 2012 R2 ストレージ ソリューションはパフォーマンスへの影響を最小限に抑え、コストを半分に削減できます。 Windows Server 2012 R2 のファイル共有オプションの詳細については、R2 Storage のダウンロード可能なホワイト [ペーパー Windows Server 2012参照してください](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)。 
  
ファイル共有を作成するためのビデオ **の手順をご覧ください**。
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>基本的なファイル共有を作成する

1. ファイル共有をホストするコンピューターにログオンします。
    
2. 共有するフォルダーを右クリックし、[プロパティ] を選択 **します**。
    
3. [共有] **タブを選択** し、[高度な共有] **をクリックします**。
    
4. [この **フォルダーの共有] をクリックします**。
    
5. **[アクセス許可]** をクリックします。
    
6. ファイル共有を **ホストしているサーバーのローカルの Administrators** グループを追加し、[ **許可:** フル コントロール、変更、読み取り権限] を付与して **、[OK]** をクリックします。
    
7. もう **一度 [OK]** をクリックし、ネットワーク パスをメモします。
    
8. [ **完了] を** クリックしてウィザードを閉じます。
    
     ![フォルダーを共有する [共有] タブ。](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>ファイル ストアが DFS 共有でホストされている場合は、次の警告が表示されます。

警告: " " の共有アクセス許可にアクセスできません \\ <domain> \<share> 。

>これは、ファイル サーバーの管理者ではない場合、またはこれが分散ファイル システム (DFS) 共有の場合に想定されます。 共有アクセス許可が既に構成されている場合、この警告は無視できます。 新しい共有の場合は、手動で共有アクセス許可を構成する方法の詳細については、ドキュメントを参照してください。

>DFS 共有の共有アクセス許可にアクセスできないので、Skype for Business Server はファイル共有にグループを明示的に設定できません。 Skype for Business Server コンポーネントが適切なアクセス許可を持つファイル共有にアクセスするには、フル コントロール共有アクセス許可を持つローカル管理者に加えて、読み取りおよび変更レベルの共有アクセス許可を持つ次の RTC グループが追加されます。
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
