---
title: ビュー内に VIS プールを作成Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: '概要: トポロジ ビルダーを使用して、ビデオ相互運用Skype for Business Serverを作成します。'
---

# <a name="create-a-vis-pool-in-skype-for-business-server"></a>ビュー内に VIS プールを作成Skype for Business Server
 
**概要:** トポロジ ビルダーを使用して、Skype for Business Server相互運用サーバー プールを作成します。
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>トポロジ ビルダーを使用して VIS または VIS プールを作成する

1. フロントエンド サーバーでトポロジ ビルダーを開きます。 トポロジ ビルダーの左側のウィンドウで、[ビデオ相互運用サーバー  プール] を右クリックし、[新しいビデオ相互運用サーバー プール **] を選択します**。 
    
2. これにより、[新しいビデオ相互運用機能サーバー プール **の作成] ウィザードが開** きます。 新しいビデオ相互運用サーバーのプール FQDN を指定し、[このプールに 1 つのサーバーがある] または [このプールに要件に基づいて複数のサーバーを持つ] を選択し、[次へ] を押 **します**。
    
    高可用性を提供するためにビデオ相互運用サーバー プールを展開する場合は、[このプールには **複数のサーバーがあります] を選択します**。 次のオプションに注意してください。 
    
    - ビデオ相互運用サーバー プールをサポートするには、DNS 負荷分散を展開する必要があります。 
    
   - 次のページの [このプール内のコンピューターを定義する] アイテムに、プール内の各サーバーの **コンピューター FQDN** をテキスト フィールドに入力し、[追加] をクリック **します**。 この手順を繰り返して、別のビデオ相互運用サーバーをプールに追加します。 プール内のすべてのコンピューターを定義した場合は、[次へ] を **押します**。
    
     高可用性を必要としないので、プールに 1 つのビデオ相互運用サーバーのみを展開する場合は、[このプールに 1 つのサーバーがある] を選択し、[ **次へ]** を押 **します**。
    
3. ドロップダウン リストから次ホップ プール/FE を選択し、[次へ] を **押します**。
    
4. VIS に関連付けるエッジ プールを選択し、[完了] を **押します**。
    
5. TCP または TLS ポートを設定します。
    
    トポロジ ビルダーの左側のウィンドウから新しく追加されたビデオ相互運用サーバーを選択し、右クリックして [プロパティの編集] **を選択します**。 要件ごとに TCP または TLS ポートを有効または更新し、[OK] を選択 **します**。 既定では TLS が追加されましたが、TCP だけが完全に Cisco Unified Communications Manager (CallManager、または CUCM) でテストされています。
    
6. ビデオ ゲートウェイを追加します。 これを行うには、[共有コンポーネント] を展開し、[ビデオ ゲートウェイ] を右クリックし **、[** 新しいビデオ ゲートウェイ **] を選択します**。
    
7. ビデオ ゲートウェイの FQDN または IP アドレスを指定します。 ビデオ ゲートウェイは、サブドメインまたは別のドメインに含めできます。 システムの VTC で使用される CUCM は、ビデオ ゲートウェイとして機能します。
    
8. 必要に応じて、IPv4 または IPv6 を選択します。 構成済みのすべての IP アドレスを使用するか、サービスの使用を選択した IP アドレスに制限できます。
    
9. ビデオ ゲートウェイのリッスン ポートを選択します。 トランスポート プロトコル (TCP または TLS) を選択し、ビデオ SIP トランク用にセットアップされたビデオ相互運用サーバーに関連付ける。 ビデオ ゲートウェイのトランスポート プロトコルは、VIS 用に構成されたトランスポート プロトコルと一致する必要があります。
    
10. 上記の手順が完了すると、対応する SIP ビデオ トランクが追加されます。 SIP ビデオ トランクを右クリックし、追加したトランクを選択します。 ビデオ SIP トランク名、関連付けられたビデオ相互運用サーバー、SIP トランスポート プロトコル、およびポートはすべて変更できます。 
    
    > [!NOTE]
    >  ビデオ相互運用サーバーは、1:N トランクをサポートします。 したがって、複数のトランクを追加できます。これは単一のビデオ相互運用サーバーに関連付けられるため、各トランクは別のビデオ ゲートウェイで終了します。 この制限は、特定のビデオ ゲートウェイに 1 つのトランクのみを持ち、そのトランクを展開に定義Skype for Business Serverです。
  
11. 「Create and publish new topology in the [2015](../../deploy/install/create-and-publish-new-topology.md)」の説明に従って、トポロジ ドキュメントSkype for Business Serverします。
    
    > [!NOTE]
    > 復元性を向上させるために、2 つ目のビデオ相互運用サーバーまたは VIS プール、またはバックアップ フロント エンド プールを構成できます。 詳細 [については、「復元メカニズム](../../plan-your-deployment/video-interop-server.md#resiliency) 」を参照してください。
  
トポロジ ビルダーを使用して実行されるタスクはすべて完了する必要があります。 新しい VIS サーバーまたはサーバーへのソフトウェアのインストールに進みます。
## <a name="see-also"></a>関連項目

[サーバーに VIS サーバーの役割を展開Skype for Business Server](deploy-the-vis-server-role.md)

[ビデオ相互運用サーバーの計画をSkype for Business Server](../../plan-your-deployment/video-interop-server.md)
  
[2015 年に新しいトポロジをSkype for Business Serverする](../../deploy/install/create-and-publish-new-topology.md)
