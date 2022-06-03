---
title: Skype for Business Serverでファイル共有を作成する
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
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
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: '概要: Skype for Business Serverのインストールの一環として、Windows サーバー ファイル共有を作成する方法について説明します。'
ms.openlocfilehash: 12ea75a11470d5730c891b1c738a3337ccb28ac8
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860728"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Skype for Business Serverでファイル共有を作成する
 
**概要：** Skype for Business Serverのインストールの一環として、Windows Server ファイル共有を作成する方法について説明します。
  
Skype for Business Serverには、トポロジ全体のコンピューターがファイルを交換できるように、ファイル共有が必要です。 ファイル共有の作成は、Skype for Business Serverのインストール プロセスの手順 2/ 8 です。 手順 1 ~ 5 は、任意の順序で実行できます。 ただし、図に示すように、手順 6、7、および 8 を順番に実行し、手順 1 ~ 5 を実行する必要があります。 ファイル共有の計画の詳細については、[Skype for Business Serverの環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)または [Skype for Business Server 2019 のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)に関するページを参照してください。
  
![概要図。](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>基本的なファイル共有を作成する

このセクションでは、基本的なWindows サーバー ファイル共有の作成について説明します。 Skype for Business Serverでは、基本的なWindows サーバー ファイル共有がサポートされています。 ただし、高可用性は明示的に提供されません。 高可用性環境では、分散ファイル システム (DFS) ファイル共有をお勧めします。 高可用性ファイル共有と DFS の詳細については、「[Skype for Business Serverでの高可用性とディザスター リカバリーの計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。
  
> [!NOTE]
> Windows Server 2012 R2 は、Windows サーバー プラットフォームを使用して、Storage Area Network (SAN) に似たファイル共有ソリューションを提供する上で大きな飛躍的な進歩を遂げました。 従来の SAN ベースのアプライアンスと比較すると、Windows Server 2012 R2 ストレージ ソリューションは、パフォーマンスへの影響を最小限に抑えてコストを半分に削減できます。 Windows Server 2012 R2 のファイル共有オプションの詳細については、ダウンロード可能なホワイト ペーパー [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)を参照してください。 
  
**ファイル共有を作成** するためのビデオ手順をご覧ください。
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>基本的なファイル共有を作成する

1. ファイル共有をホストするコンピューターにログオンします。
    
2. 共有するフォルダーを右クリックし、[ **プロパティ**] を選択します。
    
3. [ **共有** ] タブを選択し、[ **高度な共有**] をクリックします。
    
4. [ **このフォルダーの共有**] をクリックします。
    
5. **[アクセス許可]** をクリックします。
    
6. ファイル共有をホストしているサーバーのローカル **管理者** グループを追加 **し、許可: フル コントロール、変更、読み取り** 権限を付与して、[OK] をクリック **します**。
    
7. もう一度 **[OK] を** クリックし、ネットワーク パスをメモします。
    
8. [ **完了] を** クリックしてウィザードを閉じます。
    
     ![フォルダーを共有するための [共有] タブ。](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>ファイル ストアが DFS 共有でホストされている場合は、次の警告が表示されます。

`Warning: Unable to access share permissions for "\\<domain>\<share>".`

>これは、ファイル サーバーの管理者ではない場合、またはこれが分散ファイル システム (DFS) 共有の場合に必要です。 共有アクセス許可が既に構成されている場合、この警告は無視できます。 新しい共有の場合は、共有アクセス許可を手動で構成する方法の詳細については、ドキュメントを参照してください。

>DFS 共有の共有アクセス許可にアクセスできないため、Skype for Business Serverファイル共有にグループを明示的に設定することはできません。 Skype for Business Server コンポーネントが適切なアクセス許可を持つファイル共有にアクセスできるようにするには、フル コントロール共有アクセス許可を持つローカル管理者に加えて、次の RTC グループに読み取りおよび変更レベルの共有アクセス許可が追加されていることを確認します。
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
