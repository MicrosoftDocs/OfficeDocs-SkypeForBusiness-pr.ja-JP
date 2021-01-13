---
title: Skype for Business Server で VIS プールを作成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: '概要: トポロジ ビルダーを使用して、Skype for Business Server にビデオ相互運用サーバー プールを作成します。'
ms.openlocfilehash: 7c6f45b232151d99cbce169826c8110cf4a8d494
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802057"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Skype for Business Server で VIS プールを作成する
 
**概要:** トポロジ ビルダーを使用して、Skype for Business Server にビデオ相互運用サーバー プールを作成します。
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>トポロジ ビルダーを使用して VIS または VIS プールを作成する

1. フロントエンド サーバーでトポロジ ビルダーを開きます。 トポロジ ビルダーの左側のウィンドウで、[ビデオ相互運用サーバー プール] を右クリックし、[新しいビデオ相互運用サーバー プール]**を選択します**。 
    
2. これにより、新しいビデオ相互運用サーバー **プールの作成ウィザードが開** きます。 新しいビデオ相互運用サーバーのプール FQDN を指定し、このプールに 1 つのサーバーが含まれるか、このプールの要件に基づいて複数のサーバーを持つサーバーを選択して、[次へ] を押 **します**。 
    
    高可用性を実現するためにビデオ相互運用サーバー プールを展開する場合は、[このプールには複数のサーバーがあります] **を選択します**。 このオプションには、次の注意が必要です。 
    
    - ビデオ相互運用サーバー プールをサポートするには、DNS 負荷分散を展開する必要があります。 
    
   - 次のページで、[このプール内のコンピューターの定義] 項目で、プール内の各サーバーのコンピューター **FQDN** をテキスト フィールドに入力し、[追加] をクリック **します**。 この手順を繰り返して、別のビデオ相互運用サーバーをプールに追加します。 プール内のすべてのコンピューターを定義した後、[次へ] を **押します**。
    
     高可用性を必要としないので、プールにビデオ相互運用サーバーを 1 つしか展開しない場合は、[このプールに 1 つのサーバーがある] を選択し、[次へ] を押 **します**。
    
3. ドロップダウン リストから次ホップ プール/FE を選択し、[次へ] を押 **します**。
    
4. VIS に関連付けるエッジ プールを選択し、[完了] を **押します**。
    
5. TCP ポートまたは TLS ポートを設定します。
    
    トポロジ ビルダーの左側のウィンドウから新しく追加したビデオ相互運用サーバーを選択し、右クリックして [プロパティの編集] **を選択します**。 要件に従って TCP ポートまたは TLS ポートを有効または更新し **、[OK]** を選択します。 既定では TLS が追加されます。ただし、CISCO Unified Communications Manager (CallManager または CUCM) を使用して完全にテストされたのは TCP のみです。
    
6. ビデオ ゲートウェイを追加します。 これを行うには、[共有コンポーネント] を展開し、[ **ビデオ** ゲートウェイ] を右クリックして [新しいビデオ ゲートウェイ] **を選択します**。
    
7. ビデオ ゲートウェイの FQDN または IP アドレスを指定します。 ビデオ ゲートウェイは、サブドメインまたは別のドメインに含めできます。 システムの VTC で使用される CUCM は、ビデオ ゲートウェイとして機能します。
    
8. 必要に応じて、IPv4 または IPv6 を選択します。 構成済みのすべての IP アドレスを使用するか、サービスの使用を選択した IP アドレスに制限できます。
    
9. ビデオ ゲートウェイのリッスン ポートを選択します。 トランスポート プロトコル (TCP または TLS) を選択し、ビデオ SIP トランク用に設定されたビデオ相互運用サーバーに関連付ける。 ビデオ ゲートウェイのトランスポート プロトコルは、VIS 用に構成されたトランスポート プロトコルと一致している必要があります。
    
10. 上記の手順が完了すると、対応する SIP ビデオ トランクが追加されます。 SIP ビデオ トランクを右クリックし、追加したトランクを選択します。 ビデオ SIP トランク名、関連付けられたビデオ相互運用サーバー、SIP トランスポート プロトコル、およびポートはすべて変更できます。 
    
    > [!NOTE]
    >  ビデオ相互運用サーバーは、1:N トランクをサポートします。 したがって、複数のトランクを追加できます。複数のトランクは 1 つのビデオ相互運用サーバーに関連付けられるため、各トランクは異なるビデオ ゲートウェイで終了します。 この制限は、特定のビデオ ゲートウェイに、Skype for Business Server 展開に定義できるトランクが 1 つしか含めないという制限です。
  
11. 「Skype [for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)での新しいトポロジの作成と公開」の説明に従ってトポロジ ドキュメントを公開します。
    
    > [!NOTE]
    > 回復性を向上させるために、2 つ目のビデオ相互運用サーバーまたは VIS プール、またはバックアップ フロントエンド プールを構成できます。 詳細 [については、「復元メカニズム」](../../plan-your-deployment/video-interop-server.md#resiliency) を参照してください。
  
トポロジ ビルダーを使用して実行したタスクはすべて完了です。 新しい VIS サーバーへのソフトウェアのインストールに進みます。
## <a name="see-also"></a>関連項目

[Skype for Business Server で VIS サーバーの役割を展開する](deploy-the-vis-server-role.md)

[Skype for Business Server でのビデオ相互運用サーバーの計画](../../plan-your-deployment/video-interop-server.md)
  
[Skype for Business Server 2015 での新しいトポロジの作成と公開](../../deploy/install/create-and-publish-new-topology.md)
