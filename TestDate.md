// projects/date/TestDate.c++
// Copyright (C) 2010
// Glenn P. Downing
// Modified by Arasi Aravindhan
//             Egboh Chinedu
// --------------------------

/**To test the program:
> % g++ -ansi -pedantic -lcppunit -ldl -Wall TestDate.c++ -o
TestDate.app
> % valgrind TestDate.app >& TestDate.out**/

// --------
// includes
// --------

#include 

&lt;cstring&gt;

   // strcmp
#include 

&lt;sstream&gt;

   // ostringstream
#include 

&lt;stdexcept&gt;

 // invalid\_argument
#include 

&lt;string&gt;

    // ==

#include "cppunit/extensions/HelperMacros.h" // CPPUNIT\_TEST, CPPUNIT\_TEST\_SUITE, CPPUNIT\_TEST\_SUITE\_END
#include "cppunit/TestFixture.h"             // TestFixture
#include "cppunit/TestSuite.h"               // TestSuite
#include "cppunit/TextTestRunner.h"          // TestRunner

#include "Date.h"

// --------
// TestDate
// --------

struct TestDate : CppUnit::TestFixture {
> // ----------------
> // test\_constructor
> // ----------------

> void test\_constructor () {
> > try {
> > > const Date

&lt;int&gt;

 x(0, 1, 1600);
> > > CPPUNIT\_ASSERT(false);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(std::strcmp(e.what(), "Date::Date()") == 0);}}


> void test\_constructor\_1 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 1600);
> > > CPPUNIT\_ASSERT(true);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_constructor\_2 () {
> > try {
> > > const Date

&lt;int&gt;

 x(29, 2, 2000);
> > > CPPUNIT\_ASSERT(true);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_constructor\_3 () {
> > try {
> > > const Date

&lt;int&gt;

 x(29, 2, 1999);
> > > CPPUNIT\_ASSERT(false);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(std::strcmp(e.what(), "Date::Date()") == 0);}}


> void test\_constructor\_4 () {
> > try {
> > > const Date

&lt;int&gt;

 x(31, 3, 4545);
> > > CPPUNIT\_ASSERT(true);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_constructor\_5 () {
> > try {
> > > const Date

&lt;int&gt;

 x(31, 4, 4884);
> > > CPPUNIT\_ASSERT(false);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(std::strcmp(e.what(), "Date::Date()") == 0);}}

> void test\_constructor\_6 () {
> > try {
> > > const Date

&lt;int&gt;

 x(29, 2, 2100);
> > > CPPUNIT\_ASSERT(false);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(std::strcmp(e.what(), "Date::Date()") == 0);}}

> > void test\_constructor\_7 () {
> > > try {
> > > > const Date

&lt;int&gt;

 x(29, 2, 3000);
> > > > CPPUNIT\_ASSERT(false);}

> > > catch (std::invalid\_argument& e) {
> > > > CPPUNIT\_ASSERT(std::strcmp(e.what(), "Date::Date()") == 0);}}




> // -------------
> // test\_equal\_to
> // -------------

> void test\_equal\_to\_1 () {
> > try {
> > > const Date

&lt;int&gt;

 x(28, 2, 2000);
> > > const Date

&lt;int&gt;

 y(28, 2, 2000);
> > > CPPUNIT\_ASSERT(x == y);
> > > CPPUNIT\_ASSERT(!(x != y));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_equal\_to\_2 () {
> > try {
> > > const Date

&lt;int&gt;

 x(29, 12, 4000);
> > > const Date

&lt;int&gt;

 y(29, 12, 4000);
> > > CPPUNIT\_ASSERT(x == y);
> > > CPPUNIT\_ASSERT(!(x != y));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_equal\_to\_3 () {
> > try {
> > > const Date

&lt;int&gt;

 x(10, 11, 1999);
> > > const Date

&lt;int&gt;

 y(10, 11, 1999);
> > > CPPUNIT\_ASSERT(x == y);
> > > CPPUNIT\_ASSERT(!(x != y));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_equal\_to\_4 () {
> > try {
> > > const Date

&lt;int&gt;

 x(31, 12, 1602);
> > > const Date

&lt;int&gt;

 y(31, 12, 1602);
> > > CPPUNIT\_ASSERT(x == y);
> > > CPPUNIT\_ASSERT(!(x != y));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_equal\_to\_5 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 1600);
> > > const Date

&lt;int&gt;

 y(1, 1, 1600);
> > > CPPUNIT\_ASSERT(x == y);
> > > CPPUNIT\_ASSERT(!(x != y));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}

> // ---------
> // test\_less
> // ---------

> void test\_less\_1 () {
> > try {
> > > const Date

&lt;int&gt;

 x(27, 2, 2000);
> > > const Date

&lt;int&gt;

 y(28, 2, 2000);
> > > CPPUNIT\_ASSERT(x <  y);
> > > CPPUNIT\_ASSERT(x <= y);
> > > CPPUNIT\_ASSERT(!(x >  y));
> > > CPPUNIT\_ASSERT(!(x >= y));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_less\_2 () {
> > try {
> > > const Date

&lt;int&gt;

 x(15, 2, 1600);
> > > const Date

&lt;int&gt;

 y(1, 4, 4645);
> > > CPPUNIT\_ASSERT(x <  y);
> > > CPPUNIT\_ASSERT(x <= y);
> > > CPPUNIT\_ASSERT(!(x >  y));
> > > CPPUNIT\_ASSERT(!(x >= y));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_less\_3 () {
> > try {
> > > const Date

&lt;int&gt;

 x(16, 7, 1998);
> > > const Date

&lt;int&gt;

 y(18, 8, 1998);
> > > CPPUNIT\_ASSERT(x <  y);
> > > CPPUNIT\_ASSERT(x <= y);
> > > CPPUNIT\_ASSERT(!(x >  y));
> > > CPPUNIT\_ASSERT(!(x >= y));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_less\_4 () {
> > try {
> > > const Date

&lt;int&gt;

 x(15, 6, 4445);
> > > const Date

&lt;int&gt;

 y(15, 6, 4446);
> > > CPPUNIT\_ASSERT(x <  y);
> > > CPPUNIT\_ASSERT(x <= y);
> > > CPPUNIT\_ASSERT(!(x >  y));
> > > CPPUNIT\_ASSERT(!(x >= y));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_less\_5 () {
> > try {
> > > const Date

&lt;int&gt;

 x(14, 1, 17544);
> > > const Date

&lt;int&gt;

 y(12, 11, 17544);
> > > CPPUNIT\_ASSERT(x <  y);
> > > CPPUNIT\_ASSERT(x <= y);
> > > CPPUNIT\_ASSERT(!(x >  y));
> > > CPPUNIT\_ASSERT(!(x >= y));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}



> void test\_less\_6 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 1600);
> > > const Date

&lt;int&gt;

 y(1, 1, 1600);
> > > CPPUNIT\_ASSERT(!(x <  y));
> > > CPPUNIT\_ASSERT((x <= y));
> > > CPPUNIT\_ASSERT(!(x >  y));
> > > CPPUNIT\_ASSERT((x >= y));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}



> void test\_less\_7 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 2010);
> > > const Date

&lt;int&gt;

 y(2, 1, 2010);
> > > CPPUNIT\_ASSERT(x <  y);
> > > CPPUNIT\_ASSERT(x <= y);
> > > CPPUNIT\_ASSERT(!(x >  y));
> > > CPPUNIT\_ASSERT(!(x >= y));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_less\_8 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 2000010);
> > > const Date

&lt;int&gt;

 y(2, 1, 2000010);
> > > CPPUNIT\_ASSERT(x <  y);
> > > CPPUNIT\_ASSERT(x <= y);
> > > CPPUNIT\_ASSERT(!(x >  y));
> > > CPPUNIT\_ASSERT(!(x >= y));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> // ---------
> // test\_plus
> // ---------

> void test\_plus () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 2000);
> > > const Date

&lt;int&gt;

 y(1, 1, 2001);
> > > CPPUNIT\_ASSERT(x + 366 == y);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_1 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 1600);
> > > CPPUNIT\_ASSERT(x + 0 == x);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_2 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 3, 5411);
> > > > const Date

&lt;int&gt;

 y(28, 2, 5411);

> > > CPPUNIT\_ASSERT(x + (-1) == y);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_3 () {
> > try {
> > > const Date

&lt;int&gt;

 x(31, 12, 2000);
> > > > const Date

&lt;int&gt;

 y(1, 1, 2001);

> > > CPPUNIT\_ASSERT(x + 1 == y);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_4 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 1600);
> > > CPPUNIT\_ASSERT(x + 1 != x);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}




> void test\_plus\_6 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 1600);
> > > x + 1;
> > > > const Date

&lt;int&gt;

 y(1, 1, 1600);

> > > CPPUNIT\_ASSERT(x == y);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_7 () {
> > try {
> > > const Date

&lt;int&gt;

 x(12, 3, 1997);
> > > > const Date

&lt;int&gt;

 y(12, 3, 1999);

> > > CPPUNIT\_ASSERT(x + 730 == y);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_8 () {
> > try {
> > > const Date

&lt;int&gt;

 x(14, 10, 4545);
> > > > const Date

&lt;int&gt;

 y(14, 12, 4545);

> > > CPPUNIT\_ASSERT(x + 61 == y);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_9 () {
> > try {
> > > Date

&lt;int&gt;

 x(21, 2, 1887);
> > > > const Date

&lt;int&gt;

 y(21, 2, 1888);
> > > > Date

&lt;int&gt;

& z = x;
> > > > z += 365;

> > > CPPUNIT\_ASSERT(x == y);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_10 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 1600);
> > > > const Date

&lt;int&gt;

 y(31, 1, 1600);

> > > CPPUNIT\_ASSERT(x + 30 == y);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_11 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 1600);
> > > > const Date

&lt;int&gt;

 y(31, 1, 1600);

> > > CPPUNIT\_ASSERT(30 + x == y);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_12 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 1600);
> > > > const Date

&lt;int&gt;

 y(1, 1, 1601);

> > > CPPUNIT\_ASSERT(366 + x == y);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_13 () {
> > try {
> > > const Date

&lt;int&gt;

 x(5, 4, 1997);
> > > > const Date

&lt;int&gt;

 y(1, 4, 1997);

> > > CPPUNIT\_ASSERT((-4) + x == y);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_14 () {
> > try {
> > > const Date

&lt;int&gt;

 x(17, 8, 1777);
> > > > const Date

&lt;int&gt;

 y(17, 8, 1778);

> > > CPPUNIT\_ASSERT(365 + x == y);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_15 () {
> > try {
> > > const Date

&lt;int&gt;

 x(27, 9, 1801);
> > > > const Date

&lt;int&gt;

 y(27, 9, 1801);

> > > CPPUNIT\_ASSERT(0 + x == y);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_plus\_16 () {
> > try {
> > > Date

&lt;int&gt;

 x(1, 1, 1600);
> > > Date

&lt;int&gt;

& y = x;
> > > y += -1;
> > > CPPUNIT\_ASSERT(false);}

> > catch (std::invalid\_argument& e) {
> > CPPUNIT\_ASSERT(std::strcmp(e.what(), "Date::operator +=()") == 0);}}



> void test\_plus\_17 () {
> > try {
> > > Date

&lt;int&gt;

 x(31, 1, 1600);
> > > Date

&lt;int&gt;

& y = x;
> > > y += -35;
> > > CPPUNIT\_ASSERT(false);}

> > catch (std::invalid\_argument& e) {
> > CPPUNIT\_ASSERT(std::strcmp(e.what(), "Date::operator +=()") == 0);}}







> // ----------
> // test\_minus
> // ----------

> void test\_minus\_1 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 2000);
> > > const Date

&lt;int&gt;

 y(1, 1, 2001);
> > > CPPUNIT\_ASSERT(y - 366 == x);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_minus\_2 () {
> > try {
> > > const Date

&lt;int&gt;

 x(12, 1, 1604);
> > > const Date

&lt;int&gt;

 y(21, 1, 1604);
> > > CPPUNIT\_ASSERT(y - 9 == x);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_minus\_3 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 2001);
> > > const Date

&lt;int&gt;

 y(1, 1, 2000);
> > > CPPUNIT\_ASSERT(y - (-366) == x);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_minus\_4 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 1967);
> > > const Date

&lt;int&gt;

 y(1, 1, 1967);
> > > CPPUNIT\_ASSERT(y - 0 == x);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_minus\_5 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 2000);
> > > const Date

&lt;int&gt;

 y(1, 1, 2000);
> > > y - 1;
> > > CPPUNIT\_ASSERT(y == x);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_minus\_6 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 2000);
> > > const Date

&lt;int&gt;

 y(1, 1, 2000);
> > > CPPUNIT\_ASSERT(y - x == 0);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_minus\_7 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 2001);
> > > const Date

&lt;int&gt;

 y(1, 1, 2000);
> > > CPPUNIT\_ASSERT(x - y == 366);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_minus\_8 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 2000);
> > > const Date

&lt;int&gt;

 y(1, 1, 2001);
> > > CPPUNIT\_ASSERT(x - y == -366);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_minus\_9 () {
> > try {
> > > const Date

&lt;int&gt;

 x(12, 1, 2000);
> > > const Date

&lt;int&gt;

 y(15, 1, 2000);
> > > CPPUNIT\_ASSERT(y - x == 3);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_minus\_10 () {
> > try {
> > > const Date

&lt;int&gt;

 x(5, 1, 2000);
> > > const Date

&lt;int&gt;

 y(5, 1, 1999);
> > > CPPUNIT\_ASSERT(x - y == 365);}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_minus\_11 () {
> > try {
> > > Date

&lt;int&gt;

 x(1, 1, 1600);
> > > Date

&lt;int&gt;

&y = x;
> > > y -= 1;
> > > CPPUNIT\_ASSERT(false);}

> > catch (std::invalid\_argument& e) {
> > CPPUNIT\_ASSERT(std::strcmp(e.what(), "Date::operator -=()") == 0);}}


> void test\_minus\_12 () {
> > try {
> > > Date

&lt;int&gt;

 x(31, 1, 1600);
> > > Date

&lt;int&gt;

&y = x;
> > > y -= 31;
> > > CPPUNIT\_ASSERT(false);}

> > catch (std::invalid\_argument& e) {
> > CPPUNIT\_ASSERT(std::strcmp(e.what(), "Date::operator -=()") == 0);}}




> // -----------
> // test\_output
> // -----------

> void test\_output\_1 () {
> > try {
> > > const Date

&lt;int&gt;

 x(16, 6, 2008);
> > > std::ostringstream out;
> > > out << x;
> > > CPPUNIT\_ASSERT(out.str() == "16 Jun 2008");}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_output\_2 () {
> > try {
> > > const Date

&lt;int&gt;

 x(1, 1, 1999);
> > > std::ostringstream out;
> > > out << x;
> > > CPPUNIT\_ASSERT(out.str() == "1 Jan 1999");}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_output\_3 () {
> > try {
> > > const Date

&lt;int&gt;

 x(27, 12, 1602);
> > > std::ostringstream out;
> > > out << x;
> > > CPPUNIT\_ASSERT(out.str() == "27 Dec 1602");}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_output\_4 () {
> > try {
> > > const Date

&lt;int&gt;

 x(4, 7, 1776);
> > > std::ostringstream out;
> > > out << x;
> > > CPPUNIT\_ASSERT(out.str() == "4 Jul 1776");}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_output\_5 () {
> > try {
> > > const Date

&lt;int&gt;

 x(29, 2, 2004);
> > > std::ostringstream out;
> > > out << x;
> > > CPPUNIT\_ASSERT(out.str() == "29 Feb 2004");}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_output\_6 () {
> > try {
> > > const Date

&lt;int&gt;

 x(29, 12, 2004);
> > > std::ostringstream out;
> > > out << x;
> > > CPPUNIT\_ASSERT(out.str() == "29 Dec 2004");}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}



> // --------------
> // test\_leap\_year
> // --------------

> void test\_leap\_year\_1 () {
> > try {
> > > CPPUNIT\_ASSERT(Date

&lt;int&gt;

(1, 1, 2000).leap\_year());}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_leap\_year\_2 () {
> > try {
> > > CPPUNIT\_ASSERT(!(Date

&lt;int&gt;

(1, 1, 1999).leap\_year()));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_leap\_year\_3 () {
> > try {
> > > CPPUNIT\_ASSERT(Date

&lt;int&gt;

(1, 1, 2004).leap\_year());}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_leap\_year\_4 () {
> > try {
> > > CPPUNIT\_ASSERT(!(Date

&lt;int&gt;

(1, 1, 2100).leap\_year()));}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}


> void test\_leap\_year\_5 () {
> > try {
> > > CPPUNIT\_ASSERT(Date

&lt;int&gt;

(1, 1, 2400).leap\_year());}

> > catch (std::invalid\_argument& e) {
> > > CPPUNIT\_ASSERT(false);}}

> > void test\_leap\_year\_6 () {
> > > try {
> > > > CPPUNIT\_ASSERT(!(Date

&lt;int&gt;

(1, 1, 1700).leap\_year()));}

> > > catch (std::invalid\_argument& e) {
> > > > CPPUNIT\_ASSERT(false);}}

> > > void test\_leap\_year\_7 () {
> > > > try {
> > > > > CPPUNIT\_ASSERT(!(Date

&lt;int&gt;

(1, 1, 1800).leap\_year()));}

> > > > catch (std::invalid\_argument& e) {
> > > > > CPPUNIT\_ASSERT(false);}}

> > > > void test\_leap\_year\_8 () {
> > > > > try {
> > > > > > CPPUNIT\_ASSERT(!(Date

&lt;int&gt;

(1, 1, 1900).leap\_year()));}

> > > > > catch (std::invalid\_argument& e) {
> > > > > > CPPUNIT\_ASSERT(false);}}



> // -----
> // suite
> // -----

> CPPUNIT\_TEST\_SUITE(TestDate);
> CPPUNIT\_TEST(test\_constructor);
> CPPUNIT\_TEST(test\_constructor\_1);
> CPPUNIT\_TEST(test\_constructor\_2);
> CPPUNIT\_TEST(test\_constructor\_3);
> > CPPUNIT\_TEST(test\_constructor\_4);
> > CPPUNIT\_TEST(test\_constructor\_5);
> > CPPUNIT\_TEST(test\_constructor\_6);
> > CPPUNIT\_TEST(test\_constructor\_7);

> CPPUNIT\_TEST(test\_equal\_to\_1);
> CPPUNIT\_TEST(test\_equal\_to\_2);
> CPPUNIT\_TEST(test\_equal\_to\_3);
> CPPUNIT\_TEST(test\_equal\_to\_4);
> CPPUNIT\_TEST(test\_equal\_to\_5);
> CPPUNIT\_TEST(test\_less\_1);
> CPPUNIT\_TEST(test\_less\_2);
> CPPUNIT\_TEST(test\_less\_3);
> CPPUNIT\_TEST(test\_less\_4);
> CPPUNIT\_TEST(test\_less\_5);
> > CPPUNIT\_TEST(test\_less\_6);
> > > CPPUNIT\_TEST(test\_less\_7);
> > > > CPPUNIT\_TEST(test\_less\_8);

> CPPUNIT\_TEST(test\_plus);
> CPPUNIT\_TEST(test\_plus\_1);
> CPPUNIT\_TEST(test\_plus\_2);
> > CPPUNIT\_TEST(test\_plus\_3);
> > CPPUNIT\_TEST(test\_plus\_4);
> > // CPPUNIT\_TEST(test\_plus\_5);
> > > CPPUNIT\_TEST(test\_plus\_6);
> > > CPPUNIT\_TEST(test\_plus\_7);
> > > CPPUNIT\_TEST(test\_plus\_8);
> > > CPPUNIT\_TEST(test\_plus\_9);
> > > CPPUNIT\_TEST(test\_plus\_10);
> > > CPPUNIT\_TEST(test\_plus\_11);
> > > CPPUNIT\_TEST(test\_plus\_12);
> > > CPPUNIT\_TEST(test\_plus\_13);
> > > CPPUNIT\_TEST(test\_plus\_14);
> > > CPPUNIT\_TEST(test\_plus\_15);
> > > CPPUNIT\_TEST(test\_plus\_16);
> > > CPPUNIT\_TEST(test\_plus\_17);

> CPPUNIT\_TEST(test\_minus\_1);
> CPPUNIT\_TEST(test\_minus\_2);
> CPPUNIT\_TEST(test\_minus\_3);
> CPPUNIT\_TEST(test\_minus\_4);
> CPPUNIT\_TEST(test\_minus\_5);
> > CPPUNIT\_TEST(test\_minus\_6);
> > CPPUNIT\_TEST(test\_minus\_7);
> > CPPUNIT\_TEST(test\_minus\_8);
> > CPPUNIT\_TEST(test\_minus\_9);
> > CPPUNIT\_TEST(test\_minus\_10);
> > CPPUNIT\_TEST(test\_minus\_11);
> > CPPUNIT\_TEST(test\_minus\_12);

> CPPUNIT\_TEST(test\_output\_1);
> CPPUNIT\_TEST(test\_output\_2);
> CPPUNIT\_TEST(test\_output\_3);
> CPPUNIT\_TEST(test\_output\_4);
> CPPUNIT\_TEST(test\_output\_5);
> CPPUNIT\_TEST(test\_output\_6);
> CPPUNIT\_TEST(test\_leap\_year\_1);
> CPPUNIT\_TEST(test\_leap\_year\_2);
> CPPUNIT\_TEST(test\_leap\_year\_3);
> CPPUNIT\_TEST(test\_leap\_year\_4);
> CPPUNIT\_TEST(test\_leap\_year\_5);

> CPPUNIT\_TEST\_SUITE\_END();};

// ----
// main
// ----

int main () {
> using namespace std;
> ios\_base::sync\_with\_stdio(false);  // turn off synchronization with C I/O
> cout << "TestDate.c++" << endl;

> CppUnit::TextTestRunner tr;
> tr.addTest(TestDate::suite());
> tr.run();

> cout << "Done." << endl;
> return 0;}