---
title: "Smart Audio Capture: Unlocking Efficiency at Scale for a Regtech Client"
image: /article/airfocus-ioinvpqe738-unsplash.jpg
date: 2024-02-05T06:13:26.005Z
author: Insighture Technology
tags:
  - Regtech
  - success story
categories: []
draft: false
---
Target audience: C-level execs, startup founders and Fintech leadership

In Regulatory technology, otherwise known as regtech, the demand for innovative solutions has never been more crucial. Precision matters but so does efficiency. As leaders you may be steering the course of your business. It is smart to consider the transformative power of technology that not only ensures regulatory compliance for your clients but also redefines the very fabric of operational efficiency at scale. Regulatory tech is rapidly evolving for that very reason. 

According to recent studies, the global market for it is projected to reach $41 billion by 2030, with annual spending on regtech set to reach $200 billion by 2028. To reiterate, there is big demand for it from the top management globally. Despite Gen AI making  huge noise in finance, the status quo of regtech applications in the industry last year was recordkeeping and acute monitoring of communication channels. With 67% of financial institutions incorporating regtech solutions into their operations, the impact of technology on regulatory processes is undeniable. Such IT solutions may just be the ticket to gaining a competitive edge in an ever-evolving marketplace, especially fintech.

In this blog post, we will share how audio capture technology can become a powerful resource in the regtech toolkit. 

> A deep dive into how we as a consultancy provided a client with an advanced solution to reinforce compliance protocols, reduce regulatory risks, and ensure the highest standards of confidentiality in their virtual interactions.

# Client overview

The client is a regulatory company based in the bustling financial hub of Singapore. With a focus on the financial sector, they offer a suite of innovative products designed to streamline compliance processes, mitigate risks, and ensure adherence to ever-evolving regulatory frameworks. Their main service offering is anti-money laundering (AML) and Know Your Customer (KYC) solutions and they leverage advanced data analytics and AI to deliver unparalleled accuracy and efficiency in identifying and verifying customer identities. 

The client’s products cater to a diverse range of financial institutions, from multinational banks to emerging fintech startups. The demographics impacted by their solutions include compliance officers, risk management professionals, and even end-consumers. Benefits include heightened security and data protection, and enhancing overall trust in the financial services users receive. By enhancing compliance processes, they contribute to the overall integrity and transparency of the financial ecosystem in Singapore.

![](/article/edi-kurniawan-knr3v0tz0ia-unsplash.jpg)

**The client had the following pain points when we engaged with them:**

* Dealing with the escalating complexity of compliance requirements. Automated solutions are needed to adapt to regulatory changes and ensure continuous compliance.
* There is a rising threat of financial fraud. Staying proactive is no longer an afterthought, part of the reason why the company empowers their clients by offering advanced monitoring and detection tools. We had an opening to add value to what they offer.

# The Challenge

Their finance client conducts regular virtual meetings for internal discussions and client interactions. These meetings often involve the exchange of sensitive financial information and discussions that are subject to regulatory scrutiny. The impact of the proposed solution would have a compounded effect on operations as well as a significant impact on risk management.

> The client approached us with a unique problem: the need to connect remote users through online Zoom and Microsoft Teams meetings, extract their audio, and save it locally. 

# Our unique approach with this regtech solution

* To tackle the client's challenge, our team devised a unique approach leveraging Teams Web SDK for Teams meetings and a customized C++ program using Zoom Native Windows SDK for Zoom meetings. 
* For Teams meetings, our React-side implementation connected to the meeting URL via Teams Web SDK. This allowed us to act as an agent within the meeting, capturing raw audio data from remote users as byte streams. These streams were then transmitted to the backend through a socket connection.
* The solution for Zoom meetings involved the creation of a separate C++ program using the Zoom Native Windows SDK. This program hosted a Zoom agent, establishing a connection to the Zoom meeting. The Zoom agent efficiently extracted raw audio data from remote users, sending the data to the backend through a socket connection.
* At the backend, raw audio byte data underwent a meticulous processing. Raw data was sent to a TCP server, and its URL was provided to FFMpeg as one input audio stream. Simultaneously, physical audio data from audio devices was extracted and sent to FFMpeg as other input audio streams. 

The magic unfolded as all these audio streams were merged into different audio channels, resulting in a final, seamlessly merged audio data. This was then saved in the HLS playlist format, encapsulating the essence of the meeting in .m3u8 files and separate .ts files.

# How this played out inside our remote teams

We worked on this as a 4-member team dividing up the work into the following priorities.

1. Creating a Teams meeting agent using the Teams Web SDK. 
2. Creating the Zoom C++ application using the Zoom Windows Native SDK. 
3. Translating audio to text by leveraging Azure Cognitive Services. 
4. Identifying the active speaker in remote meetings. 

![](/article/web-sockets.png)

# Using the right tools, methods and frameworks for intelligent audio capture

![](/article/image4.png)

**Automated processing and analysis.**

The efficiency gains achieved with our audio capture solution were amplified through the incorporation of [Azure Cognitive Services](https://learn.microsoft.com/en-us/azure/architecture/data-guide/technology-choices/cognitive-services). Leveraging speech-to-text capabilities, we automated the transcription of audio data from virtual meetings. This not only significantly reduced manual intervention but also expedited the processing and analysis of vast amounts of information. Azure's robust AI algorithms ensured high accuracy in transcription, enhancing the overall reliability of our solution.

**Integration with existing regtech infrastructure.**

Our team seamlessly integrated the audio capture solution with the client's existing regtech infrastructure, fostering a cohesive ecosystem. Leveraging Azure's compatibility and flexibility, we ensured that the solution seamlessly interfaced with the client's regulatory technology stack. This integration not only streamlined operations but also allowed for a unified approach to compliance management, eliminating data silos and enhancing overall efficiency.

**Security is non-negotiable, especially in regtech.**

Our development team approached the development of the audio capture solution with an unwavering focus on protecting the extracted audio data. We ensured that the audio data captured from virtual meetings remained impenetrable to unauthorized access. 

**Dynamic collaboration with every iteration.**

A hallmark of our consulting expertise lies in our transparent and collaborative engagement style. Throughout the development process, we maintained open lines of communication with the client, providing regular progress updates and seeking feedback at every step of the process. Our team actively sought client input to refine and enhance the solution continuously. 

**Post-implementation support.**

Our commitment to the client extends well beyond the deployment phase. Post-implementation, our team remains dedicated to providing continuous support and maintenance services. This ensures that the audio capture solution evolves with the client's needs, guaranteeing its long-term success.

# Major outcomes of the solution

We architected audio extraction and saving components from scratch, eliminating the need for third-party services. 

> This slashed the administrative overheads to nearly zero for the client.

We implemented a good and viable solution to the client's problem, integrating this solution into the client's existing application.

We separated the Teams and Zoom applications from the main backend and facilitated communication through sockets. In case of failure in Teams or Zoom implementations, the meeting will be disconnected, but the rest of the application won't crash. Users can restart remote meetings without interruption, saving time.

Since we implemented communication via socket connections, the application runs asynchronously, ensuring that logic won't block the main thread. This approach makes the application more efficient both in terms of resources and time.

![](/article/608a5d363f913-1619680566.png)

# How Insighture can help solve compliance and more

The success of this regtech solution resonates with leaders aiming to optimize operations, enhance collaboration, and surpass industry standards. We hope we were able to give you a quick glance into the practical applications of astute technology consulting in the growing area of regulatory compliance, especially the compounding impact of any and all efficiency. Australian financial advisers, this one is for you.\
\
If you are looking at optimising your operations and reducing the reliance on manual work or if you intend to add value services to your existing processes through digital transformation but are not too sure how then we could help you for your digital transformation vision. [Get in touch with our Solutions Lead](https://www.insighture.com/contact) to start your digital transformation journey.
