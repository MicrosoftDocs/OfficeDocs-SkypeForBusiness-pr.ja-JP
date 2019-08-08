---
title: Skype for Business Server で VIS プールを作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: '概要: トポロジビルダーを使用して、Skype for Business Server でビデオ相互運用機能サーバープールを作成します。'
ms.openlocfilehash: dc97fde4447778be20cb60d86cddac65b663c321
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235663"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Skype for Business Server で VIS プールを作成する
 
**概要:** トポロジビルダーを使用して、Skype for Business Server でビデオ相互運用サーバープールを作成します。
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>トポロジ ビルダーを使用して VIS または VIS プールを作成する

1. フロントエンド サーバーでトポロジ ビルダーを開きます。 Topology Builder の左側のウィンドウで、[**ビデオ相互運用機能サーバー**プール] を右クリックし、[**新しいビデオ相互運用機能サーバープール**] を選びます。 
    
2. この操作を行うと、[**ビデオ相互運用サーバー プールの新規作成**] ウィザードが表示されます。 新しいビデオ相互運用サーバーのプール FQDN を指定し、**このプールに1つのサーバーが**あるか、またはこのプールに要件に基づいて**複数のサーバーが**あるかを選択して、[**次へ**] をクリックします。
    
    高可用性を実現するためにビデオ相互運用機能サーバープールを展開する場合は、[**このプールは複数のサーバー**を使用する] を選びます。 このオプションを使用する場合は次の点に注意してください。 
    
    - ビデオ相互運用サーバープールをサポートするには、DNS の負荷分散を展開する必要があります。 
    
   - 次のページの [**このプール内のコンピューターを定義します**] の項目で、プール内の各サーバーの**コンピューターの FQDN** をテキスト フィールドに入力して、[**追加**] をクリックします。 この手順を繰り返して、別のビデオ相互運用サーバーをプールに追加します。 プール内のすべてのコンピューターを定義したら、[**次へ**] をクリックします。
    
     高可用性を必要としないため、プールに1つのビデオ相互運用サーバーのみを展開する場合は、[**このプールは1台のサーバー**を使用する] を選択し、[**次へ**] をクリックします。
    
3. ドロップダウン リストから次ホップ プール/FE を選択して、[**次へ**] をクリックします。
    
4. VIS と関連付けるエッジ プールを選択して、[**完了**] をクリックします。
    
5. TCP ポートまたは TLS ポートを設定します。
    
    新しく追加された [トポロジビルダー] の左側のウィンドウから、新しく追加したビデオ相互運用サーバーを選び、右クリックして、[**プロパティの編集**] を選びます。 要件に応じて TCP ポートまたは TLS ポートを有効にするか更新して、[**OK**] を選択します。 既定では TLS が追加されますが、Cisco ユニファイドコミュニケーションマネージャー (CallManager、または CUCM) を使用して、TCP のみが完全にテストされています。
    
6. ビデオ ゲートウェイを追加します。この操作を行うには、[共有コンポーネント] を展開して、[**ビデオ ゲートウェイ**] を右クリックして、[**新しいビデオ ゲートウェイ**] を選択します。
    
7. ビデオ ゲートウェイの FQDN または IP アドレスを指定します。ビデオ ゲートウェイは、サブドメインまたは別のドメインに含めることができます。システムの VTC により使用される CUCM は、ビデオ ゲートウェイの役割を果たします。
    
8. IPv4 と IPv6 のいずれか適切な方を選択します。すべての構成済み IP アドレスを使用するか、サービスの使用を選択済みの IP アドレスに限定することができます。
    
9. ビデオ ゲートウェイのリッスン ポートを選択します。 トランスポートプロトコル (TCP または TLS) を選択して、ビデオ SIP トランク用に設定されたビデオ相互運用サーバーに関連付けます。 ビデオ ゲートウェイのトランスポート プロトコルは、VIS 向けに構成されているトランスポート プロトコルと一致する必要があります。
    
10. 上記の手順の完了後、対応する SIP ビデオ トランクが追加されます。 その SIP ビデオ トランクを右クリックして、追加されたばかりのトランクを選択します。 ビデオ SIP トランク名、関連付けられたビデオ相互運用サーバー、SIP トランスポートプロトコル、ポートのすべてを変更することができます。 
    
    > [!NOTE]
    >  ビデオ相互運用機能サーバーでは、1: N trunks がサポートされています。 このため、複数の trunks を追加できます。これは、各トランクが異なるビデオゲートウェイ上で終了する1つのビデオ相互運用サーバーに関連付けられています。 制限として、特定のビデオゲートウェイには、Skype for Business Server の展開に定義できるトランクが1つだけ含まれていることが挙げられます。
  
11. 「 [Skype For Business Server 2015 で新しいトポロジを作成して発行する](../../deploy/install/create-and-publish-new-topology.md)」の説明に従って、トポロジドキュメントを公開します。
    
    > [!NOTE]
    > 回復性を向上させるために、2つ目のビデオ相互運用サーバーまたは VIS プール、またはバックアップフロントエンドプールを構成することができます。 詳細については、「[Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency)」を参照してください。
  
トポロジ ビルダーを使用して実行するすべてのタスクはこれで完了します。 新しい VIS サーバー (複数可) へのソフトウェアのインストール作業に進みます。
## <a name="see-also"></a>関連項目

[VIS server の役割を Skype for Business Server に展開する](deploy-the-vis-server-role.md)

[Skype for Business Server のビデオ相互運用機能サーバーを計画する](../../plan-your-deployment/video-interop-server.md)
  
[Skype for Business Server 2015 での新しいトポロジの作成および公開](../../deploy/install/create-and-publish-new-topology.md)
