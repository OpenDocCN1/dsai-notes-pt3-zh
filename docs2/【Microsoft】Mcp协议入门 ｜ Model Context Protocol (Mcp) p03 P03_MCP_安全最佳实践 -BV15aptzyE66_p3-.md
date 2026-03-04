# 【Microsoft】Mcp协议入门 ｜ Model Context Protocol (Mcp) p03 P03_MCP_安全最佳实践 -BV15aptzyE66_p3-

![](img/b74bb9dc21aa7681bf5e38c453895898_0.png)

Hey there， in this chapter， we're discussing one of the most important topics in AI development。

 security。If you're building with MCP， it's not just about making things smart。

 it's about making them safe and trust me， MCP introduces some new security challenges that you won't find in traditional software。

 so let's talk about those challenges and how you can defend against them。

The model context protocol unlocks powerful capabilities by allowing AI systems to interact with tools。

 APIs and data， but with that powers comes new risk like prompt injection。

 tool poisoning and dynamic tool modification these threats can lead to things like data exfiltration。

 privacy breaches， or even an AI system executing unintended actions。

 all because of something hidden and a prompt， The good news you can absolutely defend against them。

 but it starts with understanding them， so let's walk through the most common risk one by one。

Earlier MCP specs assumed you'd row your own OO 2。0 authentication server That's not ideal for most devs As of April 2025。

 MCP servers can now delegate off to external identity providers like Microsoft InterID。

 which is a huge improvement， but even with this update， token mismanagement is a real concern。

Some folks might be tempted to let the client pass its token straight to the downstream resource called token Pass through。

This is explicitly forbidden in the MTP spec because it introduces a mess of problems；

 clients can bypass critical security controls， it muddies the audit trail。

 and it can break trust boundaries between services the bottom line only accept token's issue specifically for the MTP server。

If you're using Azure， tools like API management， Microsoft IntraID。

 and the official MCP security Guide will walk you through best practices。

Now let's talk permissions MCCP servers often get access to sensitive data。

 but if you're not careful， they might get too much access， for example。

 if your MCP server is meant to access sales data， it shouldn't be able to read all your enterprise files。

 stick to the principle of Le privilege， use RBC， audit your roles and review them regularly。

Now for one of the more AI specific threats， indirect prompt injection this happens when malicious instructions are hidden in external context。

 like an email， a web page or a PDF when the AI reads that content it interprets the hidden instructions and boom。

 unintended actions， leak data and potential harmful content。



![](img/b74bb9dc21aa7681bf5e38c453895898_2.png)

A related attack is tool poisoning， where the metadata of an MCP tool is tampered with。

Since LLMs rely on that metadata to decide which tools to call。

 attackers can sneak in dangerous behavior through tool descriptions or parameters。

 this is especially dangerous and hosted environments where tools can be changed after a user proves them。

 a tactic known as a rug pool。

![](img/b74bb9dc21aa7681bf5e38c453895898_4.png)

Okay， so what do you do about all of that Microsoft has a solution and it's called prompt shields and it's a game changer。

Prompt shields protect against both direct and indirect prompt injection attacks。

 they include detection and filtering。This finds malicious inputs in documents and emails。

Spotlighting。This helps a model identify what's a system instruction versus external text。

Delimiters in data marking。This clearly marks which data is trusted or untrusted。

Continuous updates from Microsoft。And it integrates with Azure content safety。

Let's not forget about supply chain security when building AI apps。

 your supply chain isn't just code， it includes models， embeddings， APIs。

 and contact providers before integrating any component， verify its source。

Use secure deployment pipelines， scan for vulnerabilities， and monitor for changes continuously。

Tools like GitHub Advvd Security Aure DevOs。And CoQO are key allies here。And remember。

 MCP inherits your environment's existing security posture， so the stronger your overall setup。

 the safer your MTP implementation will be。Here are a few essentials to include。

 Fo secure coding practices， Think O WasP Top 10 and O WasP for LLMs。Harding your servers。

Use multifactor authentication and patch regularly， enable logging and monitoring。

And design with zero trust architecture in mind。So to recap。

MCP introduces new and unique security risk， but most of them can be addressed with the right controls and a strong security posture。

And tools like Pro Shis， Azure content Safe， and GitHub Adv security help make it easier to build responsibly。



![](img/b74bb9dc21aa7681bf5e38c453895898_6.png)

In the next chapter， we're going to shift gears and get hands on walking through the end to end process of creating an MTP server all the way to deployment。

 I'll see you there。

![](img/b74bb9dc21aa7681bf5e38c453895898_8.png)