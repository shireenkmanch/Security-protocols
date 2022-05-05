# Security-protocols
Formal verification of a range of security protocols using a system for automated logic-based protocol verification.

# Introduction
Recent technologies have cleared the way for large scale application of electronic communication. The open and distributed nature of these communications implies that the communication medium is no longer completely controlled by the communicating parties. As a result, there has been an increasing demand for research in establishing secure communications over insecure networks, by means of security protocols. A protocol is defined to be a set of rules and conventions that define the communication framework between two or more agents. These agents, known as principals, can be end-users, processes or computing systems. In cryptographic protocols, part of atleast one message is encrypted. These protocols use cryptographic techniques to achieve goals such as confidentiality, authentication of principals and services, message integrity, non-repudiation, order and timeliness of the messages, and distribution of cryptographic keys. 

Unfortunately, open networks and distributed systems are vulnerable to hostile intruders (adversaries) who may try to subvert the protocol design goals. Existing flaws in the protocol design can be maliciously used by an adversary to attack the protocol and compromise the security property of the protocol. There have been several examples of security-related and cryptographic protocols that were published, believed to be sound, and later shown to have several security flaws.

# Logic-based Verification 
Logic-based verification is one of the most widely used formal verification techniques in the context of security protocols. This is due to both, the simplicity of logic-based methods and the conciseness of the proof they generate. Logic-based formal verification of cryptographic protocols aims at proving the correctness of the protocol against its goals. Modal logic consists of various statements about belief in or knowledge about messages in a distributed system, as well as inference rules for deriving new beliefs from available beliefs and/or new knowledge from available knowledge and beliefs. The BAN logic, developed by Burrow, Abadi and Needham, provided the initial impetus in applying modal logic in a proof-based environment. With the emergence of BAN, several researchers have applied various logic-based techniques for the formal verification of security protocols. All of these logics have been used successfully to identify a number of flaws in many protocols.

Logic-based security protocol verification is a deductive reasoning process. Before a deduction process proceeds, rules of inference and axioms should be specified. Then, the process proceeds in four steps:
1. Formalization of the protocol messages: Formally specify steps of a protocol in the language of the logic. 
2. Specification of the initial assumptions: Start with the initial protocol assumptions, build up logical statements after each protocol step using the logical axioms and inference rules. 
3. Specification of the protocol goals: Formally specify the desired protocol goals. 
4. Application of the logical postulates: Compare these logical statements with the desired protocol goals to see if the goals are achieved. 

The main objective of logic analysis is to test whether the desired protocol goals can be deduced from the initial assumptions and message exchanges of the protocol. The first step is to transform the informal security protocol specification into the language of the logic by expressing each message as a logical formula. This technique is called idealization and is usually done manually and hence, is error-prone. This is a limitation of logic-based verification.

The second step includes specifying the initial protocol assumptions. While the formal description of the protocol attempts to show the purpose of the components of each message in order to avoid ambiguity, the assumptions reflects the beliefs of the principals involved. The third step involves expressing the protocol goals in terms of the language of the logic. Then in the final step, logical postulates are applied and the message exchanges are examined in order to verify the four desired protocol goals. When few conclusions are found to be incompatible with the expected goals, this indicates that the protocol contains security flaws and weaknesses. If a weakness is discovered, the protocol should be redesigned and re-verified. 

 # CDVT - An automated logic-based verification tool
The cryptographic-protocol design & verification tool (CDVT) implements a verification logic using the concept of layered proving trees. The CDVT tool uses a parser to read in the formalized protocol specification along with the protocol goals and initial assumptions as a text file. The tool then applies the postulates of the implemented logic and the outcome of the automated verification result allows the user to trace the performed proofs. Therefore, if the verification failed, the user can analyze the reason for protocol failure. 

The inference rules provided in the CDVT are the standard rules of natural deduction. The axioms of the logic of knowledge express the fundamental properties of public-key cryptographic protocols. Layered Proving Trees are a specialized theorem prover for the needs of logic-based verification and it imitates the process used in manual application of logical postulates. If the application of logical postulates results in all the protocol goals being proven as valid, then the verification has succeeded and the protocol can be considered secure, provided that the initial assumptions and goals specified are correct. However, if the validity of some goals cannot be established, the verification has failed and it hints at problems or flaws in the protocol.

