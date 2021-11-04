---
title: Lync 2010 クライアント コンピューターで個人用連絡先ストアを構成する
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '概要: 従来のクライアントで使用される個人用連絡先ストアを構成します。'
ms.openlocfilehash: 9a9b5938d7e97460a6b8582f1563eeeb4c369272
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749358"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Lync 2010 クライアント コンピューターで個人用連絡先ストアを構成する
  
Skype for Business Server 2015 および Exchange Server 2016 または Exchange Server 2013 を統合する場合は、クライアントが使用する個人用連絡先ストアを構成する必要があります。 特に、Skype for Business を個人用連絡先ストアとして使用Exchangeを構成し、同時に、ユーザーが決定を上書きできないか確認する必要があります。 これは、各クライアント コンピューターでレジストリ値を作成および構成することで実行できます。
  
> [!NOTE]
> 次の手順は、Lync 2010 クライアント以前を使用しているクライアントでのみ必要です。 Lync 2013 クライアントとすべてのクライアントSkype for Business連絡先ストアの設定を上書きするオプションはありません。
  
ある 1 台のコンピューターでこの値を構成するには、次の手順を実行します。
  
1. クライアント コンピューターで、[スタート] をクリック **し、[実行** ] を **クリックします**。
2. [実行] **ダイアログ ボックス** に「regedit」と入力し、Enter キーを押します。
3. [レジストリ エディター] で、[HKEY_LOCAL_MACHINE] を展開し、[ソフトウェア] を展開し **、[** ポリシー] を展開し **、[Microsoft]** を展開し、[Communicator]**をCommunicator。**
4. 右クリックし **、[Communicator]** をポイント **し****、[DWORD (32 ビット) 値] をクリックします**。
5. 新しい値を作成した後、「PersonalContactStoreOverride」と入力し、Enter キーを押して値の名前を変更します。
6. PersonalContactStoreOverride の値が 0 に設定されていることを確認し、レジストリ エディタを閉じます。

複数のコンピューターでこれと同じ変更をする必要がある場合は、カスタム グループ ポリシー オブジェクトを作成します。 この方法の詳細については、「グループ ポリシー オブジェクトWindows 10作成[する」を参照](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)してください。
