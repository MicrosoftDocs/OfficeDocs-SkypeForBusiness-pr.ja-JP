---
title: Lync Server 2010 用のエッジ コンピューター設定エキスパンダー
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: エッジ サーバー コンピューターのプロパティを 1 つのエッジ サーバーとして、またはエッジ プールのメンバー コンピューターとして編集するには、サーバー名と IP アドレス構成設定を構成します。
---

# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用のエッジ コンピューター設定エキスパンダー
 
エッジ サーバー コンピューターのプロパティを 1 つのエッジ サーバーとして、またはエッジ プールのメンバー コンピューターとして編集するには、サーバー名と IP アドレス構成設定 **を構成** します。
  
- **内部名または FQDN**: ドメイン ネーム システム (DNS) で参照されているコンピューターの名前を入力します。 
    
- **内部 IPv4 アドレス**: このコンピューターの内部ネットワーク インターフェイス カード (NIC) の IPv4 アドレスを入力します。
    
- このコンピューターに **関連付けられている Access Edge サービス****外部 IPv4** アドレスを構成する
    
    > [!IMPORTANT]
    > エッジ サーバー構成に 1 つの IP アドレスを使用する場合は、Access Edge サービスの外部 IPv4 アドレスのみを編集できます。 他のエッジ サービスは、Access Edge サービスと同じ IPv4 アドレスを共有します。 
  
- 編集可能な場合は、このコンピューターに関連付けられている **Web 会議サービス****の外部 IPv4** アドレスを構成します。
    
- 編集可能な場合は、このコンピューターに関連付けられている **A/V Edge サービス****の外部 IPv4** アドレスを構成します。
    
- 編集可能な場合は、このコンピューターに関連 **付けられた NAT が有効なパブリック IPv4 アドレス** を構成します。
    
    > [!IMPORTANT]
    > NAT が有効な **パブリック IPv4** アドレスの構成プロパティは、A/V Edge サービスにネットワーク アドレス変換 (NAT) を提供することを選択した場合にのみ編集できます。
  
  [**OK**]: ダイアログでの変更を受け入れて確定します。
  
  [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
  [**ヘルプ**]: このヘルプ画面を表示します。
  

